# Song-reccomendation-system

*Key Functions*\n
* Uses Gradle to run
* Takes in a CSV file of song and user info, used as a database for calculations
* Can be run to display song or user stats, similarity, to generate recomendations, or generate playlists for users
* All input and output files are CSV files, with some output files having a header
* An example input file is provided below, and in the database folder. The format is song,user,rating. Ratings must be integers between 1-5 inclusive. 

song1,user1,2
song2,user1,3
song4,user1,4
song1,user2,2
song2,user2,3
song4,user2,5
song1,user3,4
song3,user3,5
song4,user3,4
song5,user3,5
song1,user4,1
song3,user4,2
song4,user4,1
song5,user5,3
song6,user5,2

*To Run*

To run, first run 'gradle build'. The function of the program is dictated by flag inputs.

To generate a file with song rating means and standard deviations, run "gradle run -q --args="<input-file>' '<output-file>'""

To generate a file with user ratings of every song, filtered for uncooperative users, run "gradle run -q --args="'<input-file>' '<output-file>' '-a'""

To generate a list of song similarites, calculated using Euclidean distance, run "gradle run -q --args="'<input-file>' '<output-file>' '-u'""

To generate a list of predicted ratings of songs by users who have not rated them, run "gradle run -q --args="'<input-file>' '<output-file>' '-p'""

To generate a list of songs a given user may enjoy based on songs they like, run "gradle run -q --args="'<input-file>' '<output-file>' '-r' 'song1' 'song2' 'song3'" where arguments passed after the '-r' flag are songs the user likes in the database.

To generate a playlist of songs a given user may enjoy based on songs they like, run "gradle run -q --args="'<input_file>' '<output_file>' '-s' 'K' '<liked_song_name1>' '<liked_song_name2>' ..." where 'K' is the number of starting centroids for K-means clustering. More than K songs may be chosen from the database, but not less. 
