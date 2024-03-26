

api_cwl 
  - Kamis 오픈데이터 중 친환경농산물 품목별가격정보 데이터 크롤링 해온 정보
  - 임정튜터님 Ver
        import requests
        import xml.etree.ElementTree as ET
        import pandas as pd
    
        url = " "
        params = {
          ('p_cert_key', ' '),
          ('p_cert_id', ),
          ('등등항목), '값')
        }
    
        response = requests.get(rl, params)


   - 위처럼 url을 연결한 다음 fromstring 메소드를 통해 XML 자료형을 처리

        root = ET.fromstring(response.text)
        row_dict = {'컬럼명' : [], '컬럼명' : [], ....}

        #반복문 사용해서 row_dict에 데이터를 넣어주기

         for i in root.findall('./data/item') :

           for j in i :
               row_dict[j.tag].append(j.text)

         df = pd.DataFrame(row_dict)
         df 
    
