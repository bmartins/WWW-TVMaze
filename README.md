# NAME

WWW::TVMaze - Interface to TVMaze API

# VERSION

Version 0.05

# SYNOPSIS

This module allows you to user TVMaze API ([http://www.tvmaze.com/api](http://www.tvmaze.com/api))

        use WWW::TVMaze;

        my $tv_maze = WWW::TVMaze->new();

        my $shows = $tv_maze->show_search('Arrow');

# METHODS

## shows

        my $show = $tv_maze->shows($id);

Returns a show by its ID

## show_search

        my $shows = $tv_maze->show_search($search_keyword);

Returns a list of shows that match your search keyword

## show_single_search

        my $show = $tv_maze->show_single_search($search_keyword);

Returns a single show that match your search keyword

## show_lookup

        my $show = $tv_maze->show_lookup( $id, $id_type ); # $id_type can be 'tvrage' or 'thetvdb' or 'imdb'

Returns a show by its TVRage ID or by its THETVDB ID

## show_seasons

        my $seasons = $tv_maze->show_seasons($show_id);

Returns all seasons of a show. Each season contains the number; the name (available for shows that give a title to each season, episode order (the total amount of episodes that will be released in the season); premiere and end date; network or web channel that specific season premiered on; and its image and summary.

## show_episode_list

        my $ep_list = $tv_maze->show_episode_list($show_id, $include_specials); # $include_specials can be 0 or 1 and is optional;

Returns a complete list of episodes for a given show. by defauls specials are not included

## show_cast

        my $cast = $tv_maze->show_cast($show_id);

Returns a list of main cast for a given show

## show_akas

        my $akas = $tv_maze->show_akas($show_id);

Returns a list of AKA's for a show

## show_index

        my $index = $tv_maze->show_index($page);  ## $page is optional, pagination starts on page 0

Returns all TV Maze shows , 250 results per page

## episode_by_number

        my $ep = $tv_maze->episode_by_number($show_id, $season, $ep_number);

Returns a show episode

## episodes_by_date

        my $eps = $tv_maze->episodes_by_date($show_id, $date);

Returns a list of episodes for a given show aired on a given date

## schedule

        my $schedule = $tv_maze->schedule($country_code, $date); # $country_code is an ISO 3166-1 code of the country, $date an ISO 8601 formatted date, both parameters are optional, defaults to 'US' and current day

Returns a complete list of episodes for the date and country provided

## full_schedule

        my $schedule = $tv_maze->full_schedule();

Returns a list of all future episodes known to TVmaze

## people_search

        my $people = $tv_maze->people_search($search_keyword);

Returns a list of persons that match your search keyword

## people

        my $people = $tv_maze->people($id);

Returns a person by its ID

## person_cast_credits

        my $person_credits = $tv_maze->person_cast_credits($person_id, $emded_show); # $embed_show is optional, can be 1 or 0;

Returns alll show-level cast credits for a person

## person_crew_credits

        my $person_credits = $tv_maze->person_crew_credits($person_id, $emded_show); # $embed_show is optional, can be 1 or 0;

Returns alll show-level crew credits for a person

## updates

        my $updates = $tv_maze->updates();

Returns a list of all the shows in the database with a timestamp of when they were last updated

## error

        my $error = $tv_maze->error();

Returns the last error

## http_status

        my $http_status = $tv_maze->http_status();

Returns the last HTTP status received

# AUTHOR

Bruno Martins, `<bscmartins at gmail.com>`

# BUGS

Please report any bugs or feature requests at [https://github.com/bmartins/WWW-TVMaze](https://github.com/bmartins/WWW-TVMaze)

# SUPPORT

You can find documentation for this module with the perldoc command.

    perldoc WWW::TVMaze

# LICENSE AND COPYRIGHT

Copyright 2015 Bruno Martins.

This program is free software; you can redistribute it and/or modify it
under the terms of either: the GNU General Public License as published
by the Free Software Foundation; or the Artistic License.

See http://dev.perl.org/licenses/ for more information.
