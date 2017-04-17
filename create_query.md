# Sailor, Reserves, Boats database for SQL Learning Purpose

### DROP the table if exists

```sql
drop table Reserves;
drop table Sailors;
drop table Boats;
```

### CREATE the tables

```sql lite
create table Sailors(
       sid       int not null constraint sailors_pk primary key,
       sname     varchar2(20),
       rating    int,
       age       decimal(4,1)
);
create table Boats(
       bid       int not null constraint boat_pk primary key,
       bname     varchar2(20),
       color     varchar2(20)
);
create table Reserves(
       sid       int,
       bid       int,
       day       date,
       primary key (sid,bid,day),
       foreign key (sid) references Sailors(sid)
               ON DELETE CASCADE,
       foreign key (bid) references Boats(bid)
               ON DELETE CASCADE 
);
```

### INSERT the tuples

```sql lite
insert into Sailors (sid,sname,rating,age)
values(22,'Dustin',7,45.0);
insert into Sailors (sid,sname,rating,age)
values(29,'Brutus',1,33.0);
insert into Sailors (sid,sname,rating,age)
values(31,'Lubber',8,55.5);
insert into Sailors (sid,sname,rating,age)
values(32,'Andy',8,25.5);
insert into Sailors (sid,sname,rating,age)
values(58,'Rusty',10,35.0);
insert into Sailors (sid,sname,rating,age)
values(64,'Horataio',7,35.0);
insert into Sailors (sid,sname,rating,age)
values(71,'Zorba',10,16.0);
insert into Sailors (sid,sname,rating,age)
values(74,'Horataio',9,35.0);
insert into Sailors (sid,sname,rating,age)
values(85,'Art',3,25.5);
insert into Sailors (sid,sname,rating,age)
values(95,'Bob',3,63.5);

insert into Boats (bid,bname,color)
values(101,'Interlake','blue');
insert into Boats (bid,bname,color)
values(102,'Interlake','red');
insert into Boats (bid,bname,color)
values(103,'Clipper','green');
insert into Boats (bid,bname,color)
values(104,'Marine','red');


insert into Reserves(sid,bid,day)
values(22,101,'10-OCT-98');
insert into Reserves(sid,bid,day)
values(22,102,'10-OCT-98');
insert into Reserves(sid,bid,day)
values(22,103,'8-OCT-98');
insert into Reserves(sid,bid,day)
values(22,104,'7-OCT-98');
insert into Reserves(sid,bid,day)
values(31,102,'10-Nov-98');
insert into Reserves(sid,bid,day)
values(31,103,'6-NOV-98');
insert into Reserves(sid,bid,day)
values(31,104,'12-NOV-98');
insert into Reserves(sid,bid,day)
values(64,101,'5-SEP-98');
insert into Reserves(sid,bid,day)
values(64,102,'8-SEP-98');
insert into Reserves(sid,bid,day)
values(74,103,'8-SEP-98');
```



