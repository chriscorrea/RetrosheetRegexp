# Regular Expressions for Retrosheet Events
A collection of regular expressions to parse [Retrosheet](http://www.retrosheet.org/) events.

## Event Field
The *[event field ](http://www.retrosheet.org/eventfile.htm#5)* includes a variable-length value that captures multiple elements of a baseball play:

> The first part of an event is a description of the basic play.

> The second part is a modifier for the first part and is separated from it with a forward slash, "/". In fact, there may be more than one modifier. A typical use of modifiers is to specify hit locations. For example, "D8/78" indicates a double fielded by the center fielder on a ball hit to left center. A complete list of modifiers excepting hit locations is given below. When more than one modifier is used, each is introduced by a "/".

> The third part describes the advance of any runners, separated from the earlier parts by a period. A successful advance is indicated by a dash, "-". An out made while advancing is indicated by an X. 2-3 indicates a runner has advanced from second to third on the play. 1X2 indicates the runner was out at second advancing from first. If a base runner is not listed as advancing he remains on the base he was on. In some cases lack of advance is indicated explicitly by an advance starting and ending on the same base such as 3-3 . When put outs are made on base runners the advance field indicates fielding data and errors if they occur. See below for a complete description for advances. Note that any advances after the first are separated by semicolons.

> For example, the event "S9/L9S.2-H;1-3" should be read as: single fielded by the right fielder, line drive to short right field. The runner on 2nd scored (advanced to home), and the runner on first advanced to third.

## Outcomes
Regular expressions will match outcomes, of event_type (to identify baserunning plays), event_type, and batted_ball_type.
For example, "S9/L9S.2-H;1-3" will match an event_type value "single" and batted_ball_type value of "line_drive"

The potential outcomes are as follows:

- event_class
    - baserunning

- event_type
    - balk
    - catcher_interference
    - caught_stealing_2b
    - caught_stealing_3b
    - caught_stealing_home
    - defensive_indifference
    - double
    - double_play
    - field_error
    - field_out
    - fielders_choice
    - ground_rule_double
    - force_out
    - hit_by_pitch
    - home_run
    - intentional_walk
    - passed_ball
    - picked_off_1b
    - picked_off_2b
    - picked_off_3b
    - picked_off_1b_caught_stealing
    - picked_off_2b_caught_stealing
    - picked_off_3b_caught_stealing
    - runner_advance
    - sac_bunt
    - sac_fly
    - single
    - stolen_base_2b
    - stolen_base_3b
    - stolen_base_home
    - strikeout
    - triple
    - triple_play
    - walk
    - wild_pitch

- batted_ball_type
    - bunt
    - fly_ball
    - groundball
    - line_drive 
    - popup    

## ToDo

- Increase coverage of unusual events 
- Build tests around [strange and unusual](http://www.retrosheet.org/strange.htm) event codes. 
- Include pitch-by-pitch outcomes
