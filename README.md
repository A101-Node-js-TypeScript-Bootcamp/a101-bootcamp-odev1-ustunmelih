# Odev1

# 1. TypeScript ile Javascript arasındaki farklar

## JavaScript nedir?

JavaScript denilince aklımıza HTML ve CSS ile iskelet ve tasarımı yapılan web sitelerinin kullanıcı ile etkileşime girebilmek , interaktivite katabilmek ve web sitelerinin fonksiyonelliğini arttırabilmemmizi sağlayan bir programlama dili gelirdi.İstemci taraflı programlama kurallarına uyan bu dil web sunucusundan herhangi bir kaynağa ihtiyaç duymadan kullanıcının web tarayıcısında çalışır.Ancak JavaScript büyük projeler için tasarlanmadı ve sadece kısa kodlar içeren web uygulamaları geliştilebiliyordu.Fakat Node.js tanıtıldıktan sonra sunucu tarafı programlama için bile kullanılabilir hale geldi .Fakat JavaScript bu gelişmelerle büyürken, kodu Nesne yönelimli programlamanın gerekliliklerini gerçekleştirmede hala zorlanıyor.Örneğin JavaScript sunucu tarafında dil özellikleri sayesinde gelişimi sınırlandı. Ve bu sorunların üstesinden gelebilmek için Microsoft TypeScript’i tanıttı.

## Typescript nedir?

TypeScript, isminden de anlaşılacaı gibi JavaScript'in çözüm bulamadıgı tip kontrolü problemin çözüm bulabilmek adına Microsoft tarafından geliştirilmiş JavaScript'i de kapsayan bir üst kümedir.Javascript'in tüm özelliklerine sahiptir.TypeScript, güçlü bir şekilde yazılmış, nesne yönelimli, derlenmiş bir dildir.Kodun daha kolay okunabilmesi , hataların önlenebilmesi ve sunucu tarafında tip konrollerinin sunucu tarafında Javascript'e nazaran daha güvenli bir geliştirme ortamı yaratmıştır.Node.js ortamında veya ECMAScript 3 veya üstünü destekleyen herhangi bir web tarayıcısında çalışabilir.

## TypeScript VS JavaScript

Javascript bir betik dilidir.TypeScript, nesne yönelimli bir programlama dilidir.JavaScript öğrenmesi kolay bir dildir Fakat TypeScript öğrenmesi daha zordur çünkü hem sınıf yapılarının bilinmesi hem de Javascriptin iyi derecede bilinmesi gerekmektedir.Javascript'in bir derleyiciye ihtiyacı yoktur. TypeScript'in Javascripte dönüştürebilmek için TypeScript derleyicisi gerektirir.JavaScript, istemci tarafında çalışır.TypeScript sunucu tarafında da çalışır.JavaScript’te büyük bir geliştirici topluluğu var, ancak TypeScript Javascript gibi büyük bir topluluğa sahip değil.

# 2.Node.js ile Sunucu ayağa kaldırmak

Node js, Google Chrome webV8 isimli bir javascript motoru üzerinde V8 isimli bir javascript motoru üzerinde çalışan JavaScript ile server tarafında uygulamalar yazabileceğimiz , asenkron yapıda çalışabilen ve non-blocking javascript çalışma ortamıdır.Bu çalışmada lokalde çalışan http üzerinden server oluşturacağız.

## Paket kullanmadan server kurulumu

ilk olarak http protokolü oluşturuyoruz"const http = require('http')".Daha sonra server kurulumu için server isimli değişken oluşturup callback fonksiyonu oluşturup içerisine req"request" ve res"response" isimli parametreler veriyoruz.
Ardından url değişkeni oluşturup requeste atıyoruz"const url = req.url".Sonrasında vermek istediğimiz responsu "res.write('')"ile geri dödürüp taleplerimizi url üzerinde iletebiliyoruz.Burada önemli nokta respose kod blogu içerisinde sonlandırmak ve sayfanın talebi yerine getirdikten sonra işlemin sonlandırıldığını bildirmek .Sonrasında listen ile portu dinlemek için localhost host üzerinde 3000 portunu adresliyoruz ve tarayıcımız üzerinde "http://localhost:3000/ " olarak giriş yaptığımızda taleplerimizi sunucu üzerinde gösterebiliriz.Örneğin..

##

const http = require('http')

const server = http.createServer((req, res) => {

const url = req.url

if (url === '/') {

res.write('ana sayfa')

} else if (url === '/add') {

res.write('ekleme sayfasi')

} else {

res.write('sayfa bukunamadi')

}
res.end()
})

const port = 3000

server.listen(port, () => {
console.log(`Sunucu ${port} 'portununda çalisiyor`)
})

## Express.js kullanarak server kurulumu

Express.js bir Node.js paketidir ve web uygulama sunucu çatısı oluşturmamızda çeşitli kolaylıklar sağlar.Bu paketi kullanırken kodlama konusunda kolaylıklar sağlar.Route yöntemiyle web istekleri yönetilebilir.Populer veritabanı uygulamları ile uyumlu geliştirme ortamı sunar ve farklı uygulamalar için REST API oluşturmak mümkün hale gelmiştir.Node js çalışma ortamına Express paketi eklemek için konsol üzerinde "npm install express" çalıştırmamız yeterli olucaktır.Yülenenen tüm paketler gibi node_modules klasöründe kayıtları tutulacaktır.Express.js ile server oluşturma işlemi aşaıdaki şekildedir

##

const express = require('express')

const app = express()

app.get('/', (req, res) => {

res.send('Anasayfadasiniz')

res.end()
})

app.listen(3000, () => {
console.log('Uygulama 3000 portununda çalisiyor')
})
# a101-bootcamp-Project1-Nodejs-CRUD-operations-doc
# a101-bootcamp-Project1-Nodejs-CRUD-operations-doc
