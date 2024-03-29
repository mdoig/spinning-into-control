# Spinning Into Control
## How I Used Data to Plan a Vinyl Collection and Learn Other Musical Facts About Myself

#### by Marshall Doig

I don't know how I didn't see it coming, but since moving to the Austin area several years ago, my love for and enjoyment of music have deepened. Exposure to the scene here has also expanded my tastes and reignited some dormant ones.

To be brief, the buildup of this music renaissance happened this way, pretty much in order:

* I finally had access to consistently great radio.<sup id="a1">[1](#f1)</sup>
* I signed up for Spotify and thereby maximized my listening potential.
* I went to the Austin City Limits music festival twice, and it was amazing each time.
* I saw a few other shows, too, and even met some members of Franz Ferdinand, my favorite band ever, *completely by chance* after I saw their show.

Austin has been the perfect place for me and my love of music. Eventually, I started to think about what I could do to really go further on my music consumption and appreciation. I arrived at vinyl.

First, though, I needed a turntable and some records to spin on it. With a little research, getting the turntable would be the easy part, but how would I choose what records to buy to start my collection?

### Facing the music
I sold the idea of starting a vinyl collection to my wife by saying it would be a curated collection. That meant only albums that I (or she) absolutely love — no complete discographies for just any artist.<sup id='a2'>[2](#f2)</sup>

I started out by compiling the list of artists, a mix of my favorites and ones I've always wanted to check out more thoroughly. Then I listed every studio album for each artist. In the interest of catching the odd songs that don't make it onto studio albums,<sup id='a3'>[3](#f3)</sup> I included some EPs and compilations for certain artists where I deemed it appropriate.

Next, I had to figure out an efficient way to rate each album. I decided to build a formula that relied on a relatively simple like/dislike evaluation for each track on each album. It's not necessarily a method I would use for an in-depth critical analysis — not as the sole method, at least — but it's highly effective for deciding how listenable I think each album is, which in this case is all that matters to me.<sup id='a4'>[4](#f4)</sup>

So how does the formula work? Basically, I reverse-engineered it from trying out variations on albums I already knew intimately and picking a formula that matched up with the ballpark figure of whatever rating I might have arbitrarily given. The process went something like this:

I started with just giving a like or dislike reaction to each track. I quickly added in a "neutral" reaction<sup id='a5'>[5](#f5)</sup> and assigned a value to each reaction: 1 for liked tracks, 0.5 for neutral tracks, and 0 for disliked. The initial formula looked like this (disliked tracks aren't included in the formula because their value is always 0):

```
l = number of liked tracks
n = number of neutral tracks
t = total number of tracks on album
r = album rating
r = ((l + (n * .5)) / t) * 100
```

Here's what the formula would return with my numbers on Father John Misty's *Pure Comedy*:

```
l = 12
n = 1
t = 13
r = ((12 + (1 * .5)) / 13) * 100
r = 96.15
```

That rating looks pretty accurate; I love Father John Misty. But what about for another album? I really enjoyed Pink Floyd's debut album, *Piper at the Gates of Dawn*, but a rating of 95.45 (10 liked tracks, 1 neutral, 11 total) doesn't quite feel right. I needed to do more tinkering.

I decided the missing ingredient in the initial formula was my failure to account for songs that I *loved*<sup id='a6'>[6](#f6)</sup>. In Formula 2.0, liked tracks — that is, songs that I liked but didn't *love* — got a value of 0.9. "Starred" tracks got the full value of 1. The new formula looked like this:<sup id='a7'>[7](#f7)</sup>

```
l = number of liked tracks
s = number of starred tracks
n = number of neutral tracks
t = total number of tracks on album
r = album rating
r = ((((l - s) * .9) + s + (n * .5)) / t) * 100
```

With this new formula, the rating for *Piper* (for which I only really *loved* one track) drops from 95.45 to 87.27, still a fairly solid rating and more in line with how I feel about it. But then *Pure Comedy* (six starred tracks) drops to a rating of 91.54. That rating is still great, but I would rate that album higher.

I arrived at the final formula by simply averaging the results of the first two formulas. The resulting album rating basically corresponds to a letter grade, which is a perfect scale for me, a fairly uncritical listener.<sup id='a8'>[8](#f8)</sup> The final formula looks like this:

```
l = number of liked tracks
s = number of starred tracks
n = number of neutral tracks
t = total number of tracks on album
r = album rating
r = ((((l + (n * .5)) / t) + ((((l - s) * .9) + s + (n * .5)) / t)) / 2) * 100
```

And now the formula for *Pure Comedy*'s rating is:

```
l = 12
s = 7
n = 1
t = 13
r = ((((12 + (1 * .5)) / 13) + ((((12 - 7) * .9) + 7 + (1 * .5)) / 13)) / 2) * 100
r = 94.23
```

A rating of 94.23 is a grade of A, so I'm happy with it. Pink Floyd's *Piper* now gets a 91.36 and corresponds to an A-. If any album had all songs liked but none starred, the highest possible rating is 95. This final version of the formula is pretty great.

That is, this formula works extremely well for albums of traditional track length (between about 10 and 14 tracks). It is less forgiving to albums with fewer tracks (between 7 and 9).<sup id='a9'>[9](#f9)</sup> For longer albums,<sup id='a10'>[10](#f10)</sup> it's practically impossible to get a perfect score (all tracks starred) usually because of the sheer number of songs.

With the formula set, I started listening to all the music. Once I had a handful of ratings,<sup id='a11'>[11](#f11)</sup> I chose cutoff points for categories, which would be for figuring out which albums I would buy. I chose the first cutoff — for the best albums, no-doubt purchases — for albums where all songs were "liked" and where about 40 percent of the songs were "starred," which produces a rating of 97 or higher. A rating for an album with all "liked" but none "starred" is always 95, so setting the cutoff for the very best albums just a bit higher at 97 made sense.

With the categories set, I now had a clear guide for which albums I would add to a wantlist: all albums in the top category and a few (subject to my whims) in the next-highest level. I used Discogs to start cataloguing each record I wanted.

### Lining up the artists
With all the album ratings taken care of, I had enough leftover data to look at other aspects of my musical preferences.<sup id='a12'>[12](#f12)</sup> My first idea was to try to rank my favorite artists. This process took a very long time. It can't remember every iteration of the formula I concocted to for it; I changed it so much that I don't even think I could find a trail of its evolution. But the general arc started with my idea to simply add up the value of the rank (among all rated albums) of each artist's top three albums — the lower the sum of ranks, the better the artist. The immediate problem with that method was that not every artist had three albums to count. I moved on to trying to rank artists by median album rank, but the album count problem was always around, even when I thought I had cracked it. I finally decided to use the album ratings instead of their rank. I tried ranking artists by median album rating, album rating quartiles, difference between high album rating and low album rating, and on and on. At last, I realized I would need to use various measures. I decided to implement them all by creating a "score" for each artist. It started out like this:

```
min = artist's lowest album rating
med = artist's median album rating
max = artist's highest album rating
s = artist score
s = min + med + max
```

This came close. My initial test for a formula's success was whether Franz Ferdinand, very definitely my favorite band ever, ended up on top.<sup id='a13'>[13](#f13)</sup> Then I'd look at where the rest of the artists fell. The problem with just using the low, median, and high album ratings was that the Sex Pistols, with their solitary studio album that I gave about a 98 rating, topped the field. I obviously quite like the Pistols' lone album, but from an artist standpoint, they're definitely not my favorite ever.

I pored over the artist data. After puzzling it out for several days, I eventually stumbled upon the last two key components that made the formula sing and could really account for the "Sex Pistols problem": highest album ranking and number of starred and disliked tracks. I subtracted the value of an artist's highest-ranked album from the score (higher the rank, the fewer points off a score), and I added an artist's total number of starred tracks across all albums divided by the median of starred tracks per artist and then multiplied that by 10. I then subtracted number of disliked tracks multiplied by 10. I finally had the math I needed to get a normalized high score for a one-album wonder plunked in the middle of artists with about four or more, minimum. So here's the final formula broken down and annotated for why each measure is included.


```
s = artist score
s = min + med + max - r + (b*10) - (d*10)
```

`min = artist's lowest album rating`: 
You're only as good as your worst album; the better the lowest-rated album, the better the rank.

`med = artist's median album rating`: 
The best choice for a measure of central tendency, particularly when there are potentially so few data points for an artist's album count.

`max = artist's highest album rating`: 
Greatness is rewarded. If your best album is very highly rated, you get the full credit for it.

`r = value of rank of an artist's highest-ranking album`: 
The highest rank achievable is 1. This measure's inclusion appeared to help normalize certain overachievers in the list. For example, this was the first key to solving the "Sex Pistols problem." Because they only had one album, their `min`, `med`, and `max` were the same, but the rank of that album was 30. Taking off 30 points for that really made a difference and dropped the Pistols to about No. 8 or 9 overall.

`b = number of starred tracks per artist / median of all starred tracks across all artists`: 
This was the second key to normalizing the Pistols, pushing them down just a little more. Dividing this measure by the median<sup id='a14'>[14](#f14)</sup> also helped keep artists with longevity (or simply an extremely high number of starred tracks) from shooting up far too high; instead of getting 107 points for their starred tracks, the Beatles got just 5.94 points. By contrast, the Sex Pistols had eight starred tracks on their one album; they only got 0.44 extra points for them instead of 8. I then multiplied those totals by 10 to get a more significant amount. Those point values may not sound like they add much, but the margins were so tight at the top that the 59.4 points were enough to finally push the Beatles, with a surprisingly low minimum album rating of 72 and a median ranking of 89, all the way to the top of the list.

`d = number of disliked tracks`: 
And that's where the final measure, disliked tracks, comes in. I'm such a forgiving critic that most artists never have more than about two disliked tracks.<sup id='a15'>[15](#f15)</sup> But factoring in the number of disliked tracks, multiplying them by 10, and subtracting from the final score made a difference. The Beatles have just one disliked track from me; surprisingly, it's not "Revolution 9" but "The Long and Winding Road."<sup id='a16'>[16](#f16)</sup> The single dislike, though, was enough to bump the Beatles five points below Franz Ferdinand, into second place. (**Update, 2021-05-29:** This and a few other figures mentioned in this formula breakdown were based on the first version of the artist rankings; new ratings added since then have altered the artist scores and rankings.) And when I saw the rest of the list after running the final equation, I knew I'd found a winner. Like Radiohead talked about on *Kid A*, everything was in its right place.

To sum up, the key to cracking an artist-ranking formula based on my album ratings needed to rely on the quality of an artist's full discography *and* on the strength of an artist's individual songs. Fortunately, I had data for both.

### Mixing the rest
Once I finished laboring over the two formulas, I was free to examine at more straightforward relationships and queries. I plotted visualizations for the following six titles:

* Number of albums listened to by year of release
* Rating by year of release (grouped into decades)
* Number of albums by year I first listened to them
* Rating by year of first listen
* Rating by length of album (in minutes)
* Rating by total number of album tracks

### Running out the groove
What I enjoy about this endeavor is that it's a living project. I'll never be done with it; I get to keep adding data. As I continue to listen to music, I'll keep it updated with all the new artists and ratings. I'm likely to adjust or redo some ratings that are already entered,<sup id='a17'>[17](#f17)</sup> and I'll note any changes to the data. Thanks for taking a look!

### Footnotes
<b id="f1">1</b> [KUTX](http://kutx.org/) is the best, y'all [↩](#a1)<br>
<b id='f2'>2</b> And really, in this case, what's the point of owning *Pinkerton* but also feeling compelled to have *Raditude*? [↩](#a2)<br>
<b id='f3'>3</b> Like the Red Hot Chili Peppers' "Soul to Squeeze" [↩](#a3)<br>
<b id='f4'>4</b> Disclaimer time: The ratings are based solely on my own tastes and preferences — which could change and evolve! If I love/hate something that you hate/love, please don't take it personally. [↩](#a4)<br>
<b id='f5'>5</b> Basically, I think a song is *meh*, neither fully liked or disliked; it just exists [↩](#a5)<br>
<b id='f6'>6</b> For example, songs that, if I heard them on shuffle, I would never skip because they're just great tracks [↩](#a6)<br>
<b id='f7'>7</b> Note that starred tracks are subtracted from liked tracks. Starred tracks are also liked tracks, but they can only count toward the formula once. [↩](#a7)<br>
<b id='f8'>8</b> I would probably never give something a 2 out of 10, say, but have no problem giving something a 50/100, which corresponds to an F grade [↩](#a8)<br>
<b id='f9'>9</b> The formula is even more unforgiving to Pink Floyd albums (hi, *Animals*, with 5 tracks in all) [↩](#a9)<br>
<b id='f10'>10</b> For example, The Clash's 36-track *Sandinista!* or The Beatles' 30-track White Album [↩](#a10)<br>
<b id='f11'>11</b> Probably about 50 [↩](#a11)<br>
<b id='f12'>12</b> This was by design. I entered as many fields of data for each album that I could think of in anticipation of having a use for it after compiling all the ratings. [↩](#a12)<br>
<b id='f13'>13</b> Trust me, the band already had the numbers to always be in the top five in any formula I could come up with, so there was no torturing the numbers or formula here. [↩](#a13)<br>
<b id='f14'>14</b> 18 starred tracks per artist [↩](#a14)<br>
<b id='f15'>15</b> I'm not even sure if there is an artist with more than two [↩](#a15)<br>
<b id='f16'>16</b> Phil Spector ruined that track on *Let It Be* [↩](#a16)<br>
<b id='f17'>17</b> Opinions can change! [↩](#a17)