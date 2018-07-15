# utl_parsing_a_complex_nested_json_file_using_r_lists
Parsing a complex nested json file using r lists.  Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.


    Parsing a complex nested json file using r lists

    Extract: Positions and names for Manchester City WFC Scoccer Team

    The json file has over 100 subsections amd over
    10,000 records? with detailed stats on numerous players and teams

    github
    https://tinyurl.com/yctbmt2a
    https://github.com/rogerjdeangelis/utl_parsing_a_complex_nested_json_file_using_r_lists

    StackOverflow
    https://tinyurl.com/yczc5rct
    https://stackoverflow.com/questions/51333430/how-to-get-public-github-json-into-r-as-a-list-of-lists

    Mr Flick profile
    https://stackoverflow.com/users/2372064/mrflick

    INPUT
    =====

    %let team=1;  **  soccer team Manchester;
    %let players=11;  ** number of players;

    Original jso file
    https://tinyurl.com/y75zg5vy
    https://raw.githubusercontent.com/statsbomb/open-data/master/data/events/7298.json

    Structure of the R list
    https://tinyurl.com/yan6bp9v
    https://github.com/rogerjdeangelis/utl_parsing_a_complex_nested_json_file_using_r_lists/blob/master/utl_parsing_a_complex_nested_json_file_using_r_lists.txt

    Json file also at
    https://tinyurl.com/y9tygqke
    https://github.com/rogerjdeangelis/utl_parsing_a_complex_nested_json_file_using_r_lists/blob/master/utl_parsing_a_complex_nested_json_file_using_r_lists.json

    EXAMPLE OUTPUT
    ==============

     WORK.WANT total obs=11

      V1                     V2

      Ellie Roebuck          Goalkeeper
      Esme Beth Morgan       Right Back
      Abbie McManus          Right Center Back
      Jennifer Beattie       Left Center Back
      Demi Stokes            Left Back
      Jill Scott             Right Center Midfield
      Keira Walsh            Center Midfield
      Isobel Christiansen    Left Center Midfield
      Nikita Parris          Right Wing
      Julia Spetsmark        Left Wing
      Nadia Nadim            Center Forward


    Short section of JSON File input the more than 4000 records
    -----------------------------------------------------------

    [ {
      "id" : "1055bdac-0320-4ca4-b0a1-38624245501a",
      "index" : 1,
      "period" : 1,
      "timestamp" : "00:00:00.000",
      "minute" : 0,
      "second" : 0,
      "type" : {
        "id" : 35,
        "name" : "Starting XI"
      },
      "possession" : 1,
      "possession_team" : {
        "id" : 746,
        "name" : "Manchester City WFC"
      },
      "play_pattern" : {
        "id" : 1,
        "name" : "Regular Play"
      },
      "team" : {
        "id" : 746,
        "name" : "Manchester City WFC"
      },
      "duration" : 0.0,
      "tactics" : {
        "formation" : 433,
        "lineup" : [ {
          "player" : {
            "id" : 4637,
            "name" : "Ellie Roebuck"
          },
          "position" : {
            "id" : 1,
            "name" : "Goalkeeper"
          },
          "jersey_number" : 26
        }, {
        } ]
      }
      ......
      truncated


    RULES (JSON file mapped to R list)
    -----------------------------------

     R maps the JSON file to an R list (may not always work?)

     This is how you select element information og the goalkeeper for Manchester

     want[[1]]$tactics$lineup[[1]]$player[2])   ** this is the goalkeepers name

     want is the name of the list

     1. want[[1]] is the Manchester City WFC team
     2. want[[1]]$tactics is the section with formations and lineup
     3. want[[1]]$tactics$lineup[[i]] has players and positions information
     4. want[[1]]$tactics$lineup[[i]]$player[2] has players name ([1] has ID)
     5. want[[1]]$tactics$lineup[[i]]$position[2] has players position ([1] has position#)

    LIST of 2960
    WANT
     $ :List of 13
      ..$ id             : chr "1055bdac-0320-4ca4-b0a1-38624245501a"
      ..$ index          : int 1
      ..$ period         : int 1
      ..$ timestamp      : chr "00:00:00.000"
      ..$ minute         : int 0
      ..$ second         : int 0
      ..$ type           :List of 2
      .. ..$ id  : int 35
      .. ..$ name: chr "Starting XI"
      ..$ possession     : int 1
      ..$ possession_team:List of 2
      .. ..$ id  : int 746
      .. ..$ name: chr "Manchester City WFC"
      ..$ play_pattern   :List of 2
      .. ..$ id  : int 1
      .. ..$ name: chr "Regular Play"
      ..$ team           :List of 2
      .. ..$ id  : int 746
      .. ..$ name: chr "Manchester City WFC"
      ..$ duration       : num 0
      ..$ tactics        :List of 2
      .. ..$ formation: int 433
      .. ..$ lineup   :List of 11
      .. .. ..$ :List of 3
      .. .. .. ..$ player       :List of 2
      .. .. .. .. ..$ id  : int 4637
      .. .. .. .. ..$ name: chr "Ellie Roebuck"
      .. .. .. ..$ position     :List of 2
      .. .. .. .. ..$ id  : int 1
      .. .. .. .. ..$ name: chr "Goalkeeper"
      .. .. .. ..$ jersey_number: int 26
      .. .. .. ..........................
     $ :List of 13
      ..$ id             : chr "78e63f61-3bf1-4a9b-9c4f-27b43e5ed71e"
      ..$ index          : int 2
      ..$ period         : int 1
      ..$ timestamp      : chr "00:00:00.000"
      ..$ minute         : int 0
      ..$ second         : int 0
      ..$ type           :List of 2
      .. ..$ id  : int 35
      .. ..$ name: chr "Starting XI"
      ..$ possession     : int 1
      ..$ possession_team:List of 2
      .. ..$ id  : int 746
      .. ..$ name: chr "Manchester City WFC"
      ..$ play_pattern   :List of 2
      .. ..$ id  : int 1
      .. ..$ name: chr "Regular Play"
      ..$ team           :List of 2
      .. ..$ id  : int 745
      .. ..$ name: chr "Chelsea LFC"
      ..$ duration       : num 0

      ..$ tactics        :List of 2
      .. ..$ formation: int 352

      .. ..$ lineup   :List of 11

      .. .. ..$ :List of 3

      .. .. .. ..$ player       :List of 2

      .. .. .. .. ..$ id  : int 4640
      .. .. .. .. ..$ name: chr "Rut Hedvig Lindahl"
      .. .. .. ..$ position     :List of 2
      .. .. .. .. ..$ id  : int 1
      .. .. .. .. ..$ name: chr "Goalkeeper"
      .. .. .. ..$ jersey_number: int 1
      .. .. ..$ :List of 3


    PROCESS (All the code)
    ======================

    proc datasets lib=work kill;
    run;quit;

    %let team=1;  **  soccer team Manchester - could mao in a macro and do all teams
    %let players=11;  ** number of players;

    %utl_submit_wps64("
    libname sd1 'd:/sd1';
    options set=R_HOME 'C:/Program Files/R/R-3.3.2';
    libname wrk  sas7bdat '%sysfunc(pathname(work))';
    libname hlp  sas7bdat 'C:\Progra~1\SASHome\SASFoundation\9.4\core\sashelp';
    proc r;
    submit;
    source('C:/Program Files/R/R-3.3.2/etc/Rprofile.site', echo=T);
    library(jsonlite);
    library(purrr);
    library(dplyr);
    library(tidyverse);
    url <- 'https://raw.githubusercontent.com/statsbomb/open-data/master/data/events/7298.json';
    want <- jsonlite::read_json(url);
    str(want);
    players   <- as.data.frame(lapply( 1:&players, function(i) {do.call(rbind,want[[&team]]$tactics$lineup[[i]]$player[2])}));
    colnames(players)<-c(letters[1:&players]);
    positions <- as.data.frame(lapply( 1:&players, function(i) {do.call(rbind,want[[&team]]$tactics$lineup[[i]]$position[2])}));
    colnames(positions)<-c(letters[1:&players]);
    plypos<-cbind(t(players),t(positions));
    endsubmit;
    import r=plypos  data=wrk.want;
    run;quit;
    ");


    OUTPUT
    ======

     WORK.WANT total obs=11

      V1                     V2

      Ellie Roebuck          Goalkeeper
      Esme Beth Morgan       Right Back
      Abbie McManus          Right Center Back
      Jennifer Beattie       Left Center Back
      Demi Stokes            Left Back
      Jill Scott             Right Center Midfield
      Keira Walsh            Center Midfield
      Isobel Christiansen    Left Center Midfield
      Nikita Parris          Right Wing
      Julia Spetsmark        Left Wing
      Nadia Nadim            Center Forward

    *                _               _       _
     _ __ ___   __ _| | _____     __| | __ _| |_ __ _
    | '_ ` _ \ / _` | |/ / _ \   / _` |/ _` | __/ _` |
    | | | | | | (_| |   <  __/  | (_| | (_| | || (_| |
    |_| |_| |_|\__,_|_|\_\___|   \__,_|\__,_|\__\__,_|

    ;

    %let team=1;  ** top soccer team Manchester;
    %let players=11;  ** number of players;

    Original json file
    https://tinyurl.com/y75zg5vy

    Structure of the R list
    https://tinyurl.com/yan6bp9v

    Json file also on github
    https://tinyurl.com/y9tygqke

    *          _       _   _
     ___  ___ | |_   _| |_(_) ___  _ __
    / __|/ _ \| | | | | __| |/ _ \| '_ \
    \__ \ (_) | | |_| | |_| | (_) | | | |
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|

    ;

    see process


