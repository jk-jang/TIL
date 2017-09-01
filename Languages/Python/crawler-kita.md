# 무역협회 실시간환율정보 수집

## 1. 수집정의
### 1.1 수집 데이터
- 실시간환율정보
- 화면
![](img/2017-09-01-15-56-06.png)

### 1.2 수집 기간

- 일회성(기간 변경 가능)

## 2. 코드

### 2.1 table 생성
> HeidiSQL 사용함
```sql
CREATE TABLE `tb_exchange_temp` (
	`iso_3` VARCHAR(3) NULL DEFAULT NULL COMMENT 'ISO코드3자리',
	`country_name` VARCHAR(200) NULL DEFAULT NULL COMMENT '국가명',
	`base_exc` FLOAT NULL DEFAULT NULL COMMENT '매매기준율',
	`pre_exc` VARCHAR(50) NULL DEFAULT NULL COMMENT '전일대비',
	`change_rate` FLOAT NULL DEFAULT NULL COMMENT '등락률',
	`buy` FLOAT NULL DEFAULT NULL COMMENT '현찰살때',
	`sell` FLOAT NULL DEFAULT NULL COMMENT '현찰팔때',
	`send` FLOAT NULL DEFAULT NULL COMMENT '송금보낼때',
	`receive` FLOAT NULL DEFAULT NULL COMMENT '송금받을때',
	`base_dt` DATE NULL DEFAULT NULL COMMENT '기준일자'
)
COLLATE='utf8_general_ci'
ENGINE=InnoDB
;
```
### 2.2 DB연결 
```python
from sqlalchemy import create_engine
engine = create_engine("mysql+mysqldb://UserID:PassWord@HOST/name of db?charset=utf8")
```
### 2.1 table 생성
```python
import pandas as pd
import requests
import time
from bs4 import BeautifulSoup
from datetime import date,datetime,timedelta

startdate = date(2017, 8, 18)  
enddate = date(2017, 8, 18)
delta = enddate - startdate

colname = ['temp_country_name','base_exc','pre_exc','change_rate','buy','sell','send','receive','country_info']

for i in range(delta.days + 1):
    crwaling_date = startdate + timedelta(days=i)
    print('{} 크롤링 시작'.format(crwaling_date))
    url = "http://www.kita.net/exchangeRate_info/exchangeRate_info_list_kb.jsp?s_date1={}".format(crwaling_date)
    html = requests.get(url)
    print(html.status_code)
    html = html.text
    soup = BeautifulSoup(html, 'html.parser')    
  
    country = []
    for count in soup.select('.tableType1 th[scope=row]'):
        country.append(count.text.strip())
    print("list of country is {}\n".format(country))

    values = []
    for value in soup.select('.tableType1 td'):
        values.append(value.text.strip())
    
    time.sleep(10)

    if bool(country) == False:
        continue
    else:        
        new_values = []
        for k in range(0,len(values),8):
            j = k+8
            new_values.append(values[k:j])

        for l in range(0,len(country)):
            new_values[l].insert(0,country[l])

        df = pd.DataFrame(data=new_values, columns=colname).fillna('')
        
        df.insert(0,'country_name',df['temp_country_name'].str.split(' ',expand=True,n=1)[1])
        df.insert(0,'iso_3',df['temp_country_name'].str.split(' ',expand=True,n=1)[0])

        df.drop('country_info', axis = 1, inplace = True)
        df.drop('temp_country_name', axis = 1, inplace = True)

        execution_day = datetime.now().strftime('%Y-%m-%d')
        lst_col_idx=df.columns.size     

        df.insert(lst_col_idx,"base_dt",crwaling_date)
        df['base_exc']=df['base_exc'].str.replace(',','')
        df['buy']=df['buy'].str.replace(',','')
        df['sell']=df['sell'].str.replace(',','')
        df['send']=df['send'].str.replace(',','')
        df['receive']=df['receive'].str.replace(',','')

        df.to_sql('tb_exchange_temp',con=engine, if_exists='append', index=False)
        
        print('{} 크롤링 완료\n'.format(crwaling_date))
```
## 총평

> 1. python익숙하지 않아서 코드 엄청 더럽네
> 1. 한글처리는 발암이다.
> 1. DB로 바로 저장되니 편하다.
> 1. SQL 공부해야겠다.
