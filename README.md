1️⃣ WSL Kurulumu

Linux’u Windows üzerinde çalıştırmak için WSL (Windows Subsystem for Linux) kullanacağız.

Kurulum:

wsl --install


Versiyon kontrolü:

wsl --version

2️⃣ Temel Komutlar
pwd


Bulunduğun klasörün tam yolunu gösterir.

ls


Bulunduğun klasördeki dosya ve klasörleri listeler.

whoami


Sistemde hangi kullanıcı ile giriş yaptığını gösterir.

3️⃣ WSL Dosya Yapısı Önemli Bilgi

/mnt/c → Windows C diski

/mnt/d → Windows D diski

/home → Linux kullanıcı klasörleri

cd ~


Ana dizine (home) götürür.

4️⃣ Klasör ve Dosya İşlemleri

Klasör oluşturma:

mkdir deneme


Boş klasör silme:

rmdir deneme


İçi dolu klasör silme:

rm -r deneme


Klasöre girme:

cd deneme


Dosya oluşturma:

touch test.txt


Dosyaya yazma:

echo "Linux Öğreniyorum" > test.txt


Dosyayı okuma:

cat test.txt

⚠️ > ve >> farkı
echo "yeni veri" > test.txt


Dosyanın içini siler ve yeniden yazar

echo "ek veri" >> test.txt


Dosyanın sonuna ekleme yapar

🚨 Gerçek Hayat Uyarısı

Sunucuda:

echo "hata" > app.log


Tüm logları siler.

echo "hata" >> app.log


Sadece sona ekler.

5️⃣ Kopyalama ve Yeniden Adlandırma

Kopyalama:

cp test.txt kopya.txt


Yeniden adlandırma:

mv kopya.txt yeni.txt

6️⃣ find Komutu

Yapısı:

find [nerede] [option] [değer]


Sadece dosyalar:

find . -type f


Sadece klasörler:

find . -type d


.md dosyalarını bul:

find . -type f -name "*.md"


Kaç tane .md dosyası var:

find . -type f -name "*.md" | wc -l

7️⃣ grep Komutu (Log Analizi)
Örnek Log Oluşturalım
cd ~
mkdir logs
cd logs

echo "INFO Server started" > app.log
echo "ERROR Database connection failed" >> app.log
echo "INFO User login" >> app.log
echo "WARNING Disk almost full" >> app.log
echo "ERROR Timeout occurred" >> app.log


Logu kontrol et:

cat app.log

ERROR satırlarını bul:
grep "ERROR" app.log


Büyük/küçük harf duyarsız:

grep -i "error" app.log


Satır numarasıyla:

grep -n "ERROR" app.log


Kaç tane ERROR var:

grep "ERROR" app.log | wc -l


ERROR veya WARNING:

grep -E "ERROR|WARNING" app.log

8️⃣ Logu Canlı İzleme
tail -f app.log

Kazanımlar

Linux dosya sistemi mantığını anlama

Terminal komutlarına hakimiyet

Log analizi yapabilme

Gerçek sunucu senaryosuna hazırlık


Gerçek zamanlı log takibi yapar.
