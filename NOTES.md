* Artists have many songs
    - a Song belongs to an Artist

* Artists have many Genres through Songs

* A Genre has many Songs
    - Songs belong to a Genre

* A Genre has many Artists through Songs

Playbook:

Playbook:Active-Record-Association-Methods-dumbo-web-career-012819 fieldhouse$ rake console
[1] pry(main)> psa = Song.create(name: "Public Service Announcement")
=> #<Song:0x007fdb172930c0
    id: 1,
    name: "Public Service Announcement",
    artist_id: nil,
    genre_id: nil>

[2] pry(main)> jayz = Artist.create(name: "Jay-Z")
=> #<Artist:0x007fdb168cc780 id: 1, name: "Jay-Z">

[3] pry(main)> psa.artist = jayz
=> #<Artist:0x007fdb168cc780 id: 1, name: "Jay-Z">

[4] pry(main)> psa.artist
=> #<Artist:0x007fdb168cc780 id: 1, name: "Jay-Z">

[5] pry(main)> psa.artist.name
=> "Jay-Z"

[6] pry(main)> bp2 = Song.create(name: "Blue Print 2")
=> #<Song:0x007fdb16113520
    id: 2,
    name: "Blue Print 2",
    artist_id: nil,
    genre_id: nil>

[7] pry(main)> jayz.songs << bp2
=> [#<Song:0x007fdb16113520
    id: 2,
    name: "Blue Print 2",
    artist_id: 1,
    genre_id: nil>]

[8] pry(main)> bp2.artist
=> #<Artist:0x007fdb168cc780 id: 1, name: "Jay-Z">

[9] pry(main)> bp2.artist.name
=> "Jay-Z"
