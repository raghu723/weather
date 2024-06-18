# weather
import requests,json
api_key="920bae5097c287703c2e2331401e3ed8"
base_url="http://api.openweathermap.org/data/2.5/weather?"
city_name=input("Enter the city name: ")
complete_url=base_url+"appid="+api_key+"&q="+city_name
respponse=requests.get(complete_url)
x=response.json()
if x["cod"]!="404":
    y=x["main"]
    current_temperature=y["temp"]
    current_humidity=y["humidity"]
    z=x["weather"]
    weather_condition=z[0]["description"]
    print("Temperature (in kelvine unit)="+
          str(current_temperature)+"\n Humidity (in percentage)= "+
          str(current_humidity)+
          "\n weather_condition = "+
          str(weather_condition))
else:
    print("City not found")
