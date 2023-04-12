# laba1
- [x] 1.Скачайте библиотеку boost с помощью утилиты **wget**.
```
wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
- [x] 2.Разархивируйте скачанный файл в директорию ```~/boost_1_69_0```
```
tar -xf boost_1_69_0.tar.gz
```
- [x] 3.Подсчитайте количество файлов в директории ```~/boost_1_69_0``` не включая вложенные директории.
```
cd boost_1_69_0
tree -L 1
```
![изображение](https://user-images.githubusercontent.com/113133600/231545273-ccdc586a-3fac-42ae-8327-0f021c968d98.png)
- [x] 4.Подсчитайте количество файлов в директории ```~/boost_1_69_0``` включая вложенные директории.
``` 
tree
```
![изображение](https://user-images.githubusercontent.com/113133600/231545584-ac39ee2f-e284-4c0c-bf83-192a69ca282b.png)
- [x] 5.Подсчитайте количество заголовочных файлов, файлов с расширением ```.cpp```, сколько остальных файлов (не заголовочных и не ```.cpp```).
```
find . -name "*.cpp" | wc -l
find . -not -name "*.cpp" | wc -l
```
![изображение](https://user-images.githubusercontent.com/113133600/231546248-4b1b1e9e-2888-42ba-b837-4bdb8341b290.png)
- [x] 6.Найдите полный пусть до файла ```any.hpp``` внутри библиотеки *boost*.
```
realpath any.hpp
```
- [x] 7.Выведите в консоль все файлы, где упоминается последовательность ```boost::asio```
```
grep -lr boost::asio
```
- [x] 8.Скомпилирутйе *boost*
```
./bootstrap.sh --prefix=boost_output
./b2 install
```
- [x] 9.Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ```~/boost-libs```
```
mkdir ~/boost-libs
mv * ~/boost-libs
````
- [x] 10.Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
```
cd ~/boost-libs/
ls -sh
```
![изображение](https://user-images.githubusercontent.com/113133600/231564896-561462c7-a44a-4429-b6ff-1bd212f32f45.png)

- [x] 11.Найдите топ10 самых "тяжёлых".
```
find . -type f -exec du -h {} +|sort -rh | head -n 10
```
![изображение](https://user-images.githubusercontent.com/113133600/231565092-58745626-b8e1-4087-9b58-c1bee1b85642.png)
