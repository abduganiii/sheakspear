###  TASK 1:
SELECT plaintext FROM wordform LIMIT 10;

### TASK 2;
SELECT plaintext FROM wordform WHERE plaintext LIKE 'a%';

### TASK 3;
SELECT title, genretype FROM work WHERE genretype = 'p';

### TASK 4;
SELECT AVG(totalparagraphs) FROM work WHERE genretype = 't';

### TASK 5;
SELECT title FROM work WHERE totalwords > (SELECT AVG(totalwords) FROM work);

### TASK 6;
SELECT character.charname, speechcount, work.title FROM character LEFT JOIN character_work ON character.charid = character_work.charid LEFT JOIN work ON character_work.workid = work.workid

### TASK 7;
SELECT ROUND(avg(speechcount)), work.title FROM character JOIN character_work ON character.charid = character_work.charid JOIN work ON character_work.workid = work.workid WHERE work.title = 'Romeo and Juliet' GROUP BY work.title;

### TASK 8;
SELECT section, SUM(wordcount) as sum FROM paragraph GROUP BY section;

### TASK 9;
select charname, speechcount from character where speechcount between 15 and 30;

### TASK 10;
select title, year from work where year between 1601 and 1699;

### TASK 11;
select longtitle from work where longtitle like '%the%';

### TASK 12; 
select distinct section from paragraph;

### TASK 13;
select chapterid, description, work.title from chapter JOIN work ON chapter.workid = work.workid;

### TASK 14;
select paragraphnum, character.charname, character.speechcount from paragraph join character on paragraph.charid = character.charid;

### TASK 15;
select paragraphnum, title, work.year from paragraph join work on paragraph.workid = work.workid;