# lab01
## Laboratornaya 1

1. Скачивание *boost*
`````sh
wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
`````
Вывод:
`````sh
--2024-03-30 23:39:02--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
Resolving sourceforge.net (sourceforge.net)... 172.64.150.145, 104.18.37.111, 2606:4700:4400::6812:256f, ...
Connecting to sourceforge.net (sourceforge.net)|172.64.150.145|:443... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/ [following]
--2024-03-30 23:39:02--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download [following]
--2024-03-30 23:39:03--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 302 Found
Location: https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABmCHhotTa-VX-apTZiZfWqRNsE6XbYm0Z-aunik_Tqq9MyMCnyB20kDRYdm1Rj3ZLsYzn2B6BYQHXdddYZYKwpMXEj2Q%3D%3D&use_mirror=deac-fra&r= [following]
--2024-03-30 23:39:03--  https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABmCHhotTa-VX-apTZiZfWqRNsE6XbYm0Z-aunik_Tqq9MyMCnyB20kDRYdm1Rj3ZLsYzn2B6BYQHXdddYZYKwpMXEj2Q%3D%3D&use_mirror=deac-fra&r=
Resolving downloads.sourceforge.net (downloads.sourceforge.net)... 204.68.111.105
Connecting to downloads.sourceforge.net (downloads.sourceforge.net)|204.68.111.105|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://deac-fra.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz [following]
--2024-03-30 23:39:04--  https://deac-fra.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz
Resolving deac-fra.dl.sourceforge.net (deac-fra.dl.sourceforge.net)... 37.203.33.33
Connecting to deac-fra.dl.sourceforge.net (deac-fra.dl.sourceforge.net)|37.203.33.33|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 111710205 (107M) [application/x-gzip]
Saving to: ‘boost_1_69_0.tar.gz.6’

boost_1_69_0.tar.gz.6         100%[=================================================>] 106.53M  1.81MB/s    in 39s

2024-03-30 23:39:44 (2.74 MB/s) - ‘boost_1_69_0.tar.gz.6’ saved [111710205/111710205]
`````

2. Разархивируем скаченный файл в директорию `~/boost_1_69_0`
`````sh
tar -xzvf boost_1_69_0.tar.gz -C ~/
`````

Вывод:
https://gist.github.com/MaR1xXx/f4d82bf22f4ce7522212ee469e429da9

3. Подсчитаем количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
`````sh
ls -l ~/boost_1_69_0 | grep "^-" | wc -l >> fc.txt
`````

Вывод:
`````
12
`````

4. Подсчитаем количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
`````sh
find ~/boost_1_69_0 -type f | wc -l >> fcws.txt
`````

Вывод:
`````
61191
`````

5. Подсчитаем количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).
`````sh
find ~/boost_1_69_0 -type f -name "*.h" -o -name "*.hpp" | wc -l >> hc.txt
find ~/boost_1_69_0 -type f -name "*.cpp" | wc -l >> cc.txt
find ~/boost_1_69_0 -type f -not -name "*.h" -not -name "*.hpp" -not -name "*.cpp" | wc -l >> drugiyec.txt
`````

Вывод: (количество файлов по порядку выполнения)
`````
15208
13774
32209
`````

6. Найдём полный путь до файла `any.hpp` внутри библиотеки *boost*.
`````sh
find ~/boost_1_69_0 -name "any.hpp" >> ahp.txt
`````

Вывод:
`````
/home/MaR1xXx/boost_1_69_0/boost/type_erasure/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/hana/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/hana/fwd/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/xpressive/detail/utility/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/proto/detail/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/fusion/algorithm/query/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/fusion/include/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/type_erasure/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/hana/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/hana/fwd/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/xpressive/detail/utility/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/proto/detail/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/fusion/algorithm/query/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
/home/MaR1xXx/boost_1_69_0/boost/fusion/include/any.hpp
`````

7. Выведем в консоль все файлы, где упоминается последовательность `boost::asio`.
`````sh
grep -r "boost::asio" ~/boost_1_69_0/* >> baof.txt
`````

Вывод:

https://gist.github.com/MaR1xXx/0fe95458f64d9869f82ebfcdbb8bba2f


8. Скомпилируем *boost*.
`````sh
cd /home/MaR1xXx/boost_1_69_0
./bootstrap.sh --prefix=/home/MaR1xXx/workspace/libs
./b2 install
`````

Вывод:

https://gist.github.com/MaR1xXx/816865f9739c3cd9ea70221af656180b
https://gist.github.com/MaR1xXx/a57bfb5b706dd41c0f3c19998c430f92

9. Перенесём все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
`````sh
mv /home/MaR1xXx/boost_1_69_0/libs ~/boost-libs
`````
10. Подсчитаем сколько занимает дискового пространства каждый файл в этой директории.
`````sh
du -h ~/boost-libs/* >> dspf.txt
`````

Вывод:

https://gist.github.com/MaR1xXx/b7361285efccffaeb4a3f65bd54c74e2


11. Найдём 10 самых "тяжёлых".
`````sh
du -h ~/boost-libs/* | sort -hr | head -n 10 >> samiyetyas.txt
`````

Вывод:
`````
444M	/home/MaR1xXx/boost-libs/libs
78M	/home/MaR1xXx/boost-libs/math
78M	/home/MaR1xXx/boost-libs/libs/math
42M	/home/MaR1xXx/boost-libs/math/doc
42M	/home/MaR1xXx/boost-libs/libs/math/doc
29M	/home/MaR1xXx/boost-libs/math/test
29M	/home/MaR1xXx/boost-libs/libs/math/test
23M	/home/MaR1xXx/boost-libs/libs/beast
23M	/home/MaR1xXx/boost-libs/beast
22M	/home/MaR1xXx/boost-libs/libs/geometry
`````
