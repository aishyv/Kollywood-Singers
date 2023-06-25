# Credit where it's due - unless you're a singer

## An analysis of artist credits on Tamil Youtube music videos

This is my submission for the 2023 Lede Program's first project. 

#### Goal
This project began with a hypothesis that female singers in the Tamil music industry (in India) are not properly credited by record labels on YouTube. The aim of this project was to reveal a possible hierarchy of crediting artists for their work in Tamil film music.

### Findings
Through my analysis, I discovered that actors and music directors are top picks for credits on a music video. The names of male and female singers are missing from 96% of the sample (appeared in only 9 instances out of 237 titles). Further, there is an emerging trend of songs being sung by male music directors and actors. This could further push existing singers to the sidelines. 

### Data collection
1. Tamil film music is produced by four major record labels. I picked the YouTube channel of the biggest one (Sony Music South). It publishes a wide variety of content such as music videos, movie trailers, music launches, teasers, live performances etc. They also produce music in languages other than Tamil. (link : https://www.youtube.com/@SonyMusicSouth)
2. I used YouTube API to grab data (in json format) of 'PlaylistItems' - to ensure only Tamil music videos enter the sample. I decided to go with a random sample - and picked the six featured Tamil music playlists on their channel home page. The resulting random sample was 238 videos.
   
  | Name | Link |
  |------|------| 
  | Playlist 1 | https://www.youtube.com/playlist?list=PL_DaWb6RFQc1b64rZiW_PntzXVHwb2HjM |
  | Playlist 2 | https://www.youtube.com/playlist?list=PL_DaWb6RFQc0K6jZFSy6dJmUbCfP3ICOA |
  | Playlist 3 | https://www.youtube.com/playlist?list=PL_DaWb6RFQc2PmD6eKPJ9gD-2NLyHEbPo |
  | Playlist 4 | https://www.youtube.com/playlist?list=PL_DaWb6RFQc0I1nsKc4HOx87xo-gxoVh3 |
  | Playlist 5 | https://www.youtube.com/playlist?list=PL_DaWb6RFQc3cZM71PbYuFG-mXrH4zl1J |
  | Playlist 6 | https://www.youtube.com/playlist?list=PL_DaWb6RFQc2UqJNHQ1TQ9RB-uACJ-ZNv |
  | YouTube API docs | https://developers.google.com/youtube/v3/docs/playlistItems |

4. I also collected csv files with names of music directors, singers, actors, etc from Wikipedia/IMDB.
   
  | Name | Link |
  |------|------| 
  | Music directors | https://www.imdb.com/list/ls062857065/ |
  | Male actors (from 1980s + manually added 2 exceptions from 1970s) | https://en.wikipedia.org/wiki/List_of_Tamil_film_actors |
  | Female actors (from 1990s) | https://en.wikipedia.org/wiki/List_of_Tamil_film_actresses |
  | Indian Playback singers | https://en.wikipedia.org/wiki/List_of_Indian_playback_singers |
  | Movie directors | https://www.imdb.com/list/ls003409050/ |

6. For the last section of analysis I used IMDB data for the overall credits count of 5 music directors and 5 actors.
   
  | Name | Link |
  |------|------| 
  | Anirudh Ravichander | https://www.imdb.com/name/nm4794064/fullcredits |
  | A.R Rahman | https://m.imdb.com/name/nm0006246/fullcredits |
  | D. Imman | https://m.imdb.com/name/nm1300033/fullcredits |
  | Yuvan Shankar Raja | https://www.imdb.com/name/nm1421776/fullcredits |
  | Harris Jayaraj | https://www.imdb.com/name/nm1069415/fullcredits |

  | Joseph Vijay | https://m.imdb.com/name/nm0897201/fullcredits |
  | Sivakarthikeyan | https://m.imdb.com/name/nm4792434/fullcredits |
  | Gautham Karthik | https://m.imdb.com/name/nm5221962/fullcredits |
  | Dhanush | https://m.imdb.com/name/nm1333687/fullcredits | 
  | Vikram | https://www.imdb.com/name/nm1417314/fullcredits |

### Data Analysis:
1. Combine all music video titles into a Python list. Use strip function to standardize and remove random spacing
2. Then use split function to separate titles into lists for songname, first, second, third and fourth credit positions. Since all videos were uploaded by one channel, the title format was consistent. I could split using '|' as the separator
3. Turn all lists into one dataframe
4. Turn csv into dataframes
5. Merge all dataframes into one - with credit position coloumns, accompanied by artist type column
6. Convert to xlsx > Clean up inconsistencies and blanks in excel
7. Bring back to Jupyter Notebook as dataframe
8. run value_counts() for each artist type column
9. run groupby() + value_counts() + str.contains () to get the top 5 actors, music directors mentioned in sample
10.Compare count of credits of acting/composition with credits for playback singing
   
### New skills, approaches
- Python functions such as split, aggregate, strip, replace
Working with dataframes:
- Directly adding lists as a new column to dataframe
- Moving column position
- Renaming columns
- Deleting columns , rows
- pd.concat!!!

### What I tried to do, 
1. Calling YouTube API from Python(!!!) - tried to do this, and wasn't able to figure it out in time. So I copied the json data from the YouTube API site resulting in a world record for the most pointless scroll ever in a Jupyter Notebook. 
2. Merge function - could do this better. Resulted in a lot of pointless mess that I had to clean up manually
3. Data collection could have been more thorough. A lot of the lists were outdated, had to be updated manually. Also more thought in choosing sample, artists to study etc.

### What I wanted to do, will probably do the next time
I spent too long on collecting and cleaning up the data. Data analysis could have been more thorough. The last section of the analysis in particular was rushed and not what I had in mind. Will also need to brush up on CSS for a nice-r looking webpage. 

The project can be found here: https://aishyv.github.io/Kollywood-Singers/
