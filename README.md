<h1 align="center">InfluxDB ve Docker Kurulumu</h1>

Not: Aşağıdaki konfigürasyonlar Windows üzerinde çalıştırmak içindir. 

Öncelikle Windows için Docker Desktop indirilir. Docker compose, docker engine vs hepsi bu indirmeyle birlikte yüklenmiş olur. Docker Desktop yüklendikten sonra Docker account oluşturulur. 

Docker Desktop uygulaması üzerinde Volume, Image ve Container bilgilerinizi görebilirsiniz. Docker Desktop'un yanı sıra Command Prompt üzerinden de ilgili Docker komutları ile istediğiniz eylemleri gerçekleştirebilirsiniz.

Ayrıca çalıştırdığınız Container'larınızın üzerindeki CLI butonu ile kolayca kurduğunuz uygulamanın komut satırı arayüzüne erişebilirsiniz.





docker pull influxdb:latest

docker pull telegraf:latest

docker pull grafana:latest


docker run -d --name=influxdb -p 8086:8086 influxdb
docker run -d --name=grafana -p 3000:3000 grafana










Influx v1.x ile v2.0+ versiyonları arası mapping için gerekli komutlar:

Influx 2.0+ versiyonlarda web arayüzünde account ve bucketlar yaratıldıktan bütün konfigürasyonlar yapıldıktan sonra “influx v1 dbrp” komutu ile database ve retention policy oluşturulur. Bu ayarlar Grafana’ya Influx’I bağlarken InfluxQL seçeneği ile bağlamanızı sağlar ve “SELECT” gibi komutları kullanabilirsiniz. 

```
influx v1 dbrp create --db “database-ismi” --bucket-id “bucket id’si” –rp “retention policy adı” --token  “V2deki Token” --org “organization adı” 
 ```
Var olan databaseleri kontrol etmek için: 
```
influx v1 dbrp list --token “V2deki Token” --org “organization adı”
```
