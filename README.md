# **파이썬을 활용한 웹 크롤러**

파이썬을 이용한 간단한 웹 크롤러 실습 프로젝트입니다. <br>
[Python을 활용한 웹 크롤러 만들기 | T아카데미](https://youtu.be/TWb4xTwR0I8) 강의를 참고하였습니다. 


## 환경설정 (Window)
- [다운로드 파이썬](https://www.python.org/downloads/)
    - class path 설정하여 설치
- [selenium chromeDriver 다운로드](https://www.selenium.dev/downloads/)
    - 압축 풀어서 프로젝트에 위치
    - 어느 환경에서 돌아갈지 모르니 맥/윈도우 다 다운
- [selenium GhostDriver(PhanthomJS) 다운로드](https://phantomjs.org/download.html)
- 터미널 Selenium 다운로드: `pip install selenium`
- 터미널 BeautifulSoup 다운로드: `pip install bs4`
- 터미널 pymysql 다운로드 : `pip install pymysql`
    
## DB (MariaDB)
- Table
    - tbl_keyword
        - 크롤링 대상 키워드
    - tbl_crawlingdata
        - 컨텐츠 저장용
```MariaDB
CREATE DATABASE IF NOT EXISTS `pythondb` 
USE `PythonDB`;

DROP TABLE IF EXISTS `tbl_crawlingdata`;
CREATE TABLE IF NOT EXISTS `tbl_crawlingdata` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `title` varchar(50) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `price` varchar(50) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `area` varchar(50) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `contents` longtext COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `keyword` varchar(50) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `regdate` timestamp NULL DEFAULT current_timestamp(),
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

DELETE FROM `tbl_crawlingdata`;

DROP TABLE IF EXISTS `tbl_keyword`;
CREATE TABLE IF NOT EXISTS `tbl_keyword` (
  `keyword` varchar(50) COLLATE utf8mb4_unicode_ci NOT NULL,
  PRIMARY KEY (`keyword`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

DELETE FROM `tbl_keyword`;

INSERT INTO `tbl_keyword` (`keyword`) VALUES
	('로마'),
	('바르셀로나'),
	('파리');

```

## 참고 API
- [Selenium Python](https://selenium-python.readthedocs.io/)
- [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
- [PyMySQL](https://github.com/PyMySQL/PyMySQL)
## IDE
- PyCharm 


 