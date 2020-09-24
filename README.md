<div align="center">

## A String Tokenizer Similar To strtok\(\) in C\+\+


</div>

### Description

The following procedure acts similar to strtok in C++. Call it once with your string (S), and then everytime you call it from there on out, you can break your string apart with tokens! Included is a function StrMid() and an overload for StrMid that simulate the Mid() function in Visual Basic.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Ty](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/ty.md)
**Level**          |Beginner
**User Rating**    |3.8 (50 globes from 13 users)
**Compatibility**  |Delphi 5, Delphi 4, Pre Delphi 4
**Category**       |[String Manipulation](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/string-manipulation__7-5.md)
**World**          |[Delphi](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/delphi.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/ty-a-string-tokenizer-similar-to-strtok-in-c__7-828/archive/master.zip)





### Source Code

<FONT COLOR="009933">//Declare private string for the unit<br></FONT>
implementation<br>
var<br>
 <BLOCKQUOTE>
 TokS: string<br>
 </BLOCKQUOTE>
<br>
<FONT COLOR="009933">//Function To Get Characters From The String</FONT>
function StrMid(const sData: string; nStart: integer; nLength: integer): string; overload;<br>
begin
 <BLOCKQUOTE>
 Result := copy(sData, nStart, nLength);
 </BLOCKQUOTE>
end;<br>
<br>
<FONT COLOR="009933">//Function To Get Characters From The String</FONT>
function StrMid(const sData: string; nStart: integer): string; overload;<br>
begin<br>
 <BLOCKQUOTE>
 Result := copy(sData, nStart, Length(sData) - (nStart - 1));
 </BLOCKQUOTE>
end;<br>
<br>
<FONT COLOR="009933">//String Tokenizer function</FONT><br>
function StrTok(S: string; Tok: string = ''): string;<br>
var<br>
 <BLOCKQUOTE>
 i,<br>
 LenTok: integer;<br>
 </BLOCKQUOTE>
begin<br>
 <BLOCKQUOTE>
 if not(S = '') then begin <FONT COLOR="009933">//New String</FONT><br>
 <BLOCKQUOTE>
 TokS := S;<br>
 result := '';<br>
 Exit;<br>
 </BLOCKQUOTE>
 end;<br>
<br>
 if Tok = '' then begin<FONT COLOR="009933"> //If No Token</FONT><br>
 <BLOCKQUOTE>
 result := TokS;<br>
 Exit;<br>
 </BLOCKQUOTE>
 end;<br>
<br>
 LenTok := Length(Tok);<br>
 for i := 0 to Length(TokS) - LenTok do begin<br>
 <BLOCKQUOTE>
 if StrMid(TokS, i, LenTok) = Tok then begin<FONT COLOR="009933"> //If Token Found</FONT><br>
 <BLOCKQUOTE>
 result := StrMid(TokS, 1, i - LenTok);<br>
 TokS := StrMid(TokS, i + LenTok + 1);<br>
 Exit;<br>
 </BLOCKQUOTE>
 end;<br>
 </BLOCKQUOTE>
 end;<br>
<br>
 <FONT COLOR="009933">//If Program Reaches Here, Return The Rest Of The String</FONT><br>
 result := TokS;<br>
 TokS := '';<br>
 </BLOCKQUOTE>
end;<br>
<br>
<br>
<FONT COLOR="009933">
Therefore, for example, if you defined a string:<br></FONT>
var<br>
 <BLOCKQUOTE>
 S: string<br>
 </BLOCKQUOTE>
<br>
<FONT COLOR="009933">
and set S to 'Hello World'<br>
</FONT>
 <BLOCKQUOTE>
 S := 'Hello World';<br>
 </BLOCKQUOTE>
<br>
<FONT COLOR="009933">
and then call StrTok() like so:<br>
</FONT>
 <BLOCKQUOTE>
 StrTok(S);<br>
 </BLOCKQUOTE>
<FONT COLOR="009933">
The procedure will store the string, from now on, calling StrTok() with no S value and a token (such as a space ' '), the program will return everything in the string up to the token.<br></FONT>
<br>
EX:<br>
var<br>
 <BLOCKQUOTE>
 firstWord,<br>
 secondWord: string<br>
 </BLOCKQUOTE>
<br>
begin<br>
<br>
 <BLOCKQUOTE>
 StrTok(S);<br>
 firstWord := StrTok('', ' ');<br>
 secondWord := StrTok('', ' ');<br>
 </BLOCKQUOTE>
end;<br>
<br>
<FONT COLOR="009933">
//Doing this will break apart the string S at the token (' ') into the first word and the second word.<br></FONT>
<br>
<br>
<FONT COLOR="11FF66">
Good luck and use this code well!<br>
<FONT>

