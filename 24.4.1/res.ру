import requests
import json
baseURL='https://petstore.swagger.io/v2'
pet1='Testik1'
pet2='Testik2'

data={
  "id": 0,
  "category": {"id": 0,"name": "string"},
  "name": pet1,
  "photoUrls": ["string"],
  "tags": [{"id": 0,"name": "string"}],
  "status": "available"
}

headers = {
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    'Host': 'petstore.swagger.io',
    'Content-Length': '236',
    'Cache-Control': 'no-cache'
}

res=requests.post(f"{baseURL}/pet", headers=headers, data=json.dumps(data))
print(res.status_code)
print('Код ответа - 200 \nСоздан питомец:')
pet_id = dict(res.json())['id']

data["id"]=pet_id
data["name"]=pet2
print(f'\nменяем имя питомца на {pet2}')

res2=requests.put(f"{baseURL}/pet", headers=headers,data=json.dumps(data))
print(res2.status_code)
print('Код ответа - 200 \nВнесены изменения:')

print('\nЗапрашиваем данные с сервера о питомце по id -'+str(pet_id))
res3=requests.get( f"{baseURL}/pet/{pet_id}", headers=headers)

print(res3.status_code)
print('Код ответа - 200 \nНа сервере имеются данные:')

print('\nУдаляем данные о питомце по id -'+str(pet_id))
res4=requests.delete( f"{baseURL}/pet/{pet_id}", headers=headers)

print(res4.status_code)
print('Код ответа - 200 \nДанные о питомце удалены:')

print('\nЗаново запрашиваем данные с сервера о питомце по id -'+str(pet_id))
res5=requests.get( f"{baseURL}/pet/{pet_id}", headers=headers)

print(res5.status_code)
print('Код ответа - 200 На сервере имеются данные, Код ответа - 404 Данных нет')
