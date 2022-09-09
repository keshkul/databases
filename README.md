<h1 align="center">InfluxDB and Docker </h1>










Influx v1.x ile v2.0+ versiyonları arası mapping için gerekli komutlar:

Influx 2.0+ versiyonlarda web arayüzünde account ve bucketlar yaratıldıktan bütün konfigürasyonlar yapıldıktan sonra “influx v1 dbrp” komutu ile database ve retention policy oluşturulur. Bu ayarlar Grafana’ya Influx’I bağlarken InfluxQL seçeneği ile bağlamanızı sağlar ve “SELECT” gibi komutları kullanabilirsiniz. 

```
influx v1 dbrp create --db “database-ismi” --bucket-id “bucket id’si” –rp “retention policy adı” --token  “V2deki Token” --org “organization adı” 
 ```
Var olan databaseleri kontrol etmek için: 
```
influx v1 dbrp list --token “V2deki Token” --org “organization adı”
```
