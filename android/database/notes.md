19/3

https://gitlab.cs.cf.ac.uk/CM6122/lectures/storage_ii/blob/master/storage_ii_room.pdf

Room

Easier- helps functionality of sticking data in and getting data out

An adapter- middle man in comparision to sqlite

Takes care of heavy lifting

Live data- update data using room, auto update app

[Saving data using room](https://developer.android.com/training/data-storage/room/index.html)

Room entity- equivalent of database

Data access object- methods for accessing the database

Made appropriate choice to use a database insted of shared preferences

@Query most complex

version- structural changes change version number

**Limitations**

- If you have an owner with mulitiple pets is disallowed

- The way around is with pet class have an owner id. A pet can only have one owner
