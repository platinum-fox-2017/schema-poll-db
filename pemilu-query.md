CREATE TABLE user (
userId TEXT NOT NULL PRIMARY KEY,
password TEXT NOT NULL);

INSERT INTO user VALUES ('11111','rahasiadong');
INSERT INTO user VALUES ('22222','apaajaboleh');
INSERT INTO user VALUES ('33333','lupalagi');
INSERT INTO user VALUES ('44444','tidaktau');
INSERT INTO user VALUES ('55555','1sampai9');

CREATE TABLE voter (
voterId INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
userId TEXT NOT NULL,
first_name TEXT NOT NULL,
last_name TEXT NOT NULL,
gender TEXT NOT NULL,
age INTEGER NOT NULL,
FOREIGN KEY(userId) REFERENCES user(userId));

INSERT INTO voter VALUES (null,'11111','Eki','Fakhrureza','L',27);
INSERT INTO voter VALUES (null,'22222','Agung','Prabowo','L',27);
INSERT INTO voter VALUES (null,'33333','Ahmad','Yusuf','L',25);
INSERT INTO voter VALUES (null,'44444','Putra','Janitra','L','28');
INSERT INTO voter VALUES (null,'55555','Fitri','Ramadhani','P','40');


CREATE TABLE proyek (
idProyek INTEGER NOT NULL PRIMARY KEY,
nama TEXT NOT NULL,
nilai TEXT NOT NULL,
dueDate TEXT NOT NULL,
status TEXT NOT NULL,
keterangan TEXT);

INSERT INTO proyek VALUES (1,'EIS','200000000','2018-06-10','ON PROGRESS','Semangat');
INSERT INTO proyek VALUES (2,'HRIS','100000000','2017-12-12','DONE','Selamat');
INSERT INTO proyek VALUES (3,'Cuti Online Mobile App','150000000','2018-10-15','ON PROGRESS','Caiyo');
INSERT INTO proyek VALUES (4,'Koperasi Apps','125000000','2018-07-06','ON PROGRESS','Ganbatte');
INSERT INTO proyek VALUES (5,'SPPD Mobile Apps','225000000','2018-12-09','ON PROGRESS','Fokus');

CREATE TABLE proyekKaryawan(
idProyekKaryawan INTEGER NOT NULL PRIMARY KEY,
nik INTEGER NOT NULL,
idProyek INTEGER NOT NULL,
FOREIGN KEY(nik) REFERENCES karyawan(nik),
FOREIGN KEY(idProyek) REFERENCES proyek(idProyek));

INSERT INTO proyekKaryawan VALUES(1,05606,1);
INSERT INTO proyekKaryawan VALUES(2,05606,2);
INSERT INTO proyekKaryawan VALUES(3,05777,2);
INSERT INTO proyekKaryawan VALUES(4,05444,3);
INSERT INTO proyekKaryawan VALUES(5,05888,4);
