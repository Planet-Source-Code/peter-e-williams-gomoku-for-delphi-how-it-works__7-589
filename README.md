<div align="center">

## GoMoku for Delphi \- How It Works


</div>

### Description

This article was written to be read in conjunction with my GoMoku game. It explains the game, the code and why I did things the way that I did. You will find GoMoku v0.04 in the Delphi / Games section.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Peter E\. Williams](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/peter-e-williams.md)
**Level**          |Intermediate
**User Rating**    |4.4 (22 globes from 5 users)
**Compatibility**  |Delphi 5, Delphi 4, Pre Delphi 4
**Category**       |[Games](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/games__7-38.md)
**World**          |[Delphi](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/delphi.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/peter-e-williams-gomoku-for-delphi-how-it-works__7-589/archive/master.zip)





### Source Code

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 3.2//EN">
<HTML>
<HEAD>
<META HTTP-EQUIV="CONTENT-TYPE" CONTENT="text/html; charset=iso-8859-1">
<TITLE>Go-Moku Game - My Approach To Writing It In Delphi</TITLE>
</HEAD>
<BODY bgcolor="#ffffff">
<H1 ALIGN=CENTER>Go-Moku Game<br>
 My Approach To Writing It In Delphi</H1>
<h4 ALIGN=CENTER>by Peter E. Williams</h4>
<P>I have written version 0.04 of my GoMoku game. <i><b>Over the next few weeks
 I will re-write this article.</b></i> Previously version of GoMoku had some
 flaws in the calculation of the weights. I believe that this version is perfect
 !!! (or as near as we can get).</P>
<P>With Co-ordinate weighting on - on a blank board the cells are weighted according
 to the X,Y co-ords e.g. the corners (1,1), (1,15), (15,1), (15,15) all have
 weights of 2 = 1 + 1. The centre cell 8,8 has a weight of 16 = 8+8. </P>
<P>To see the highest cell weighting, do the following: Press D (for "Don't
 move mode"), then lay down a snowflake pattern (see below e.g. an asterisk
 with 8 legs of 4 Xs), and press W to see weights. You can then pick viewing
 weights for either X or O player.</P>
<P>This is the "snowflake" test pattern.</P>
<p><font face="Courier New, Courier, mono">X...X...X<br>
 .X..X..X.</font><br>
 <font face="Courier New, Courier, mono">..X.X.X..<br>
 ...XXX...<br>
 XXXX<i><b>?</b></i>XXXX<br>
 </font><font face="Courier New, Courier, mono">...XXX...</font><br>
 <font face="Courier New, Courier, mono">..X.X.X..<br>
 .X..X..X.<br>
 </font><font face="Courier New, Courier, mono">X...X...X<br>
 </font></p>
<p></p>
<P>Assuming Offence First ... (e.g. Offensive move rate a little higher than defensive
 moves) </P>
<P>For the X player, with the centre ( "?" ) of the snowflake being
 8,8, the highest weight will be cell 8,8 is:<br>
 = (((5^8)+90)*8)+16 = 3125736  (add 90 because the pieces are Xs and we
 are looking at the X move and *8 because there are 8 legs in the snowflake pattern.
 +16 because 16 is the rating for the X,Y co-ords for 8,8 e.g. 8+8 = 16)</P>
<P>For the O player, with the centre ( "?" ) of the snowflake being
 8,8, the highest weight will be cell 8,8 is:<br>
 = (((5^8)-90)*8)+16 = 3124296  (subtract 90 because the pieces are Xs and
 we are looking at the X move and *8 because there are 8 legs in the snowflake
 pattern. +16 because 16 is the rating for the X,Y co-ords for 8,8 e.g. 8+8 =
 16)</P>
<h2>New to ver 0.04<br>
</h2>
<P>On www.planet-source-code.com I was made aware of a bug in my GoMoku program
 with the way it calculated the weights. As a result I have rewritten completely
 the "procedure check_any_direction_for_blank" and I have removed the
 "procedure check_any_direction_for_piece" (and the procedures that
 called it) -- as these are no longer required. The other changes are: new "procedure
 check_for_winner" and "procedure count_pieces_in_line" (which
 is called by check_for_winner).</P>
<P> Also new is the Tactics menu and "Game / Do Statistics Test" (press
 T) menu. The "Tactics" menu lets you pick from 3 boolean options (for
 the tactics the computer uses to weight it's moves): (a) Defence First (unless
 winning) / Offence First, (b) Use Co-ordinate weights (yes/no), (c) Weight 4
 Blocked (e.g. whether in OXX_XO the "_" is weighted or not). </P>
<p> To use the Statistics Test press T and pick which of the tests you want to
 do e.g. there is a max of 8 tests to perform (8= 2^3). And also enter the number
 of games for each test. Total number of games in the tests = Number of tests
 to perform x Number of games for each test. e.g. 8 tests x 10 games = 80 games
 total. A report will be displayed in a richedit memo after the tests have finished.</p>
<p> Please do not use GoMoku versions before this version (as they are buggy)
 :-)))</p>
<hr>
<p> </p>
</BODY>
```

