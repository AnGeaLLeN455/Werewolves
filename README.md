program loupgarou;
uses wincrt;
var lg1,lg2,lg3,sorc,salv,chas,vlg,vovo,votevillage:string;
    votelg1,votelg2,votelg3,votesoso1,votesoso2,votesalv,votevovo,inutile1,inutile2,votechas:string;
    n,x1,x2,x3,x4,x5,x6,x7,x8,choixsoso,nv,n1,n2,n3,ns1,ns2,nsalv,nvg,nch:integer;
    tr: array [1..8] of string;
    nomj: array[1..8] of string;
    nomjalt: array[1..8] of string;
begin
Write('Bienvenue au jeu Loups-garoux. Appuyez sur une touche pour commencer.');
readkey;
clrscr;
Writeln('REGLEMENTS DU JEU');
Writeln(' ');
Writeln('Ce jeu est un "Text-based RPG".');
Writeln('Chaque joueur aura un rôle bien précis; Tous les rôles seront expliqués.');
writeln(' ');
write('Appuyez sur une touche pour commencer.');
Readkey;
clrscr;
lg1:= 'Vous êtes un loup-garou(1).';
lg2:= 'Vous êtes un loup-garou(2).'; 
lg3:= 'Vous êtes un loup-garou(3).';
sorc:= 'Vous êtes la sorcière.';
salv:= 'Vous êtes le salvateur.';
chas:= 'Vous êtes le chasseur.';
vlg:= 'Vous êtes un simple villageois.';
vovo:= 'Vous êtes la voyante.';
randomize;
x1:= random(8)+1;
repeat
x2:= random(8)+1
until x2 <> x1;
repeat
x3:= random(8)+1
until (x3 <> x2) and (x3 <> x1);
repeat
x4:= random(8)+1
until (x4 <> x3) and (x4 <> x2) and (x4 <> x1);
repeat
x5:= random(8)+1
until (x5 <> x4) and (x5 <> x3) and (x5 <> x2) and (x5 <> x1);
repeat
x6:= random(8)+1
until (x6 <> x5) and (x6 <> x4) and (x6 <> x3) and (x6 <> x2) and (x6 <> x1);
repeat
x7:= random(8)+1
until (x7 <> x6) and (x7 <> x5) and (x7 <> x4) and (x7 <> x3) and (x7 <> x2) and (x7 <> x1);
repeat
x8:= random(8)+1
until (x8 <> x7) and (x8 <> x6) and (x8 <> x5) and (x8 <> x4) and (x8 <> x3) and (x8 <> x2) and (x8 <> x1);
tr[x1]:= lg1;
tr[x2]:= lg2;
tr[x3]:= lg3;
tr[x4]:= sorc;
tr[x5]:= salv;
tr[x6]:= chas;
tr[x7]:= vlg;
tr[x8]:= vovo;
n:= 0;
repeat
n:= n + 1;
Writeln('  JOUEUR ',n,' - ENTREZ VOTRE NOM');
readln(nomj[n]);
Clrscr;
writeln(nomj[n],' - ',tr[n]);
write('Appuyez sur une touche & laissez place au prochain joueur.');
readkey;
clrscr
until n = 8;
nomjalt[1]:= nomj[1];
nomjalt[2]:= nomj[2];
nomjalt[3]:= nomj[3];
nomjalt[4]:= nomj[4];
nomjalt[5]:= nomj[5];
nomjalt[6]:= nomj[6];
nomjalt[7]:= nomj[7];
nomjalt[8]:= nomj[8];
repeat
writeln('L'+chr(39)+'ordre des joueurs dans la file sera le suivant:');
writeln(nomjalt[1],', ',nomj[1]);
writeln(nomjalt[2],', ',nomj[2]);
writeln(nomjalt[3],', ',nomj[3]);
writeln(nomjalt[4],', ',nomj[4]);
writeln(nomjalt[5],', ',nomj[5]);
writeln(nomjalt[6],', ',nomj[6]);
writeln(nomjalt[7],', ',nomj[7]);
writeln(nomjalt[8],', ',nomj[8]);
write(nomj[1],', veuillez appuyer sur une touche pour jouer votre tour.');
readkey;
clrscr;
n:=0;
repeat
n:=n + 1;
   if nomj[n]='mort'
   then begin
   writeln('vous êtes mort, laissez place à ',nomj[n+1],' pour effectuer son tour.');
   readkey;
   end
   else if tr[n] = lg1
   then begin
        writeln('Alliés: ');
        writeln(nomj[x2],' (a voté pour ',votelg2,' )');
        writeln(nomj[x3],' (a voté pour ',votelg3,' )');  
        writeln('Donnez le nom du joueur que vous voulez dévorer:');
        readln(votelg1);
        n1:= 0;
        repeat
        n1:= n1 + 1
        until votelg1 = nomj[n1];
        if n<8
        then begin
        clrscr;
        writeln('laissez place à ',nomj[n+1],' pour effectuer son tour.');
        readkey;
        end;
        end
   else if tr[n] = lg2
   then begin
        writeln('Alliés: ');
        writeln(nomj[x1],' (a voté pour ',votelg1,' )');
        writeln(nomj[x3],' (a voté pour ',votelg3,' )');
        writeln('Donnez le nom du joueur que vous voulez dévorer:');
        readln(votelg2);
        n2:= 0;
        repeat
        n2:= n2+1
        until votelg2 = nomj[n2];
        if n<8
        then begin
        clrscr;
        writeln('laissez place à ',nomj[n+1],' pour effectuer son tour.');
        readkey;
        end;
        end
   else if tr[n] = lg3
   then begin
        writeln('Alliés: ');
        writeln(nomj[x1],' (a voté pour ',votelg1,' )');
        writeln(nomj[x2],' (a voté pour ',votelg2,' )');
        writeln('Donnez le nom du joueur que vous voulez dévorer:');
        readln(votelg3);
        n3:=0;
        repeat
        n3:= n3+1
        until votelg3 = nomj[n3];
        if n<8
        then begin
        clrscr;
        writeln('laissez place à ',nomj[n+1],' pour effectuer son tour.');
        readkey;
        end;
        end
   else if tr[n] = sorc
   then begin
        write('Choisissez la potion que vous voulez utiliser: ');
        writeln('Potion de mort (Tapez 1) ou Potion de salvation (Tapez 2)');
        readln(choixsoso);
        if choixsoso = 1
        then begin
           writeln('Choisissez le joueur à tuer');
           readln(votesoso1);
           end
        else begin
             writeln('choisissez le joueur à sauver');
             readln(votesoso2);
             end;
        if n<8
        then begin
        clrscr;
        writeln('laissez place à ',nomj[n+1],' pour effectuer son tour.');
        readkey;
        end;
        end
   else if tr[n] = salv
   then begin
        writeln('Choisissez le joueur à sauver: ');
        readln(votesalv);
        if n<8
        then begin
        clrscr;
        writeln('laissez place à ',nomj[n+1],' pour effectuer son tour.');
        readkey;
        end;
        end
   else if tr[n] = vovo
   then begin
        writeln('Choisissez le joueur à espionner: ');
        readln(votevovo);
        nv:=0;
        repeat
        nv:= nv + 1
        until votevovo = nomj[nv];
        writeln('Vous consultez votre boule magique ...');
        Writeln('La carte de ',nomj[nv],' révèle le message suivant:');
        writeln('"',tr[nv],'"');
        readkey;
        if n<8
        then begin
        clrscr;
        writeln('laissez place à ',nomj[n+1],' pour effectuer son tour.');
        readkey;
        end;
        end
   else if (tr[n]= chas)
   then begin
        write('Vous n'+chr(39)+'avez pas de tour. Tapez quelque chose');
        writeln(' pour faire semblant d'+chr(39)+'en avoir un');
        read(inutile1);
        if n<8
        then begin
        clrscr;
        writeln('laissez place à ',nomj[n+1],' pour effectuer son tour.');
        readkey;
        end;
        end
   else begin
        write('Vous n'+chr(39)+'avez pas de tour. Tapez quelque chose');
        writeln(' pour faire semblant d'+chr(39)+'en avoir un');
        read(inutile2);
        if n<8
        then begin
        clrscr;
        writeln('laissez place à ',nomj[n+1],' pour effectuer son tour.');
        readkey;
        end;
        end;
clrscr
until n = 8;
ns1:=0;
ns2:=0;
nsalv:=0;
if (votelg1 = votelg2) 
then nomj[n1] := 'mort'
else if (votelg1 = votelg3)
then nomj[n1] := 'mort'
else if (votelg2 = votelg3)
then nomj[n2] := 'mort';
if nomj[x4] <> 'mort'
then begin
if choixsoso = 1
then begin
repeat
ns1:= ns1 + 1
until votesoso1 = nomj[ns1];
nomj[ns1]:= 'mort';
end
else begin
repeat
ns2:= ns2 + 1
until votesoso2 = nomj[ns2];
nomj[ns2]:= nomjalt[ns2]
end;
end;
if nomj[x5] <> 'mort'
then begin
repeat
nsalv:= nsalv + 1
until votesalv = nomj[nsalv];
nomj[nsalv]:=nomjalt[nsalv];
end;
writeln('Compte rendu de la nuit: ');
writeln(nomjalt[1],', ',nomj[1]);
writeln(nomjalt[2],', ',nomj[2]);
writeln(nomjalt[3],', ',nomj[3]);
writeln(nomjalt[4],', ',nomj[4]);
writeln(nomjalt[5],', ',nomj[5]);
writeln(nomjalt[6],', ',nomj[6]);
writeln(nomjalt[7],', ',nomj[7]);
writeln(nomjalt[8],', ',nomj[8]);
Writeln('-VOTE JOURNALIERE- Qui avez-vous voté contre ?');
readln(votevillage);
nvg:=0;
if votevillage = 'personne'
then clrscr
else begin
repeat
nvg:= nvg + 1
until votevillage = nomj[nvg];
nomj[nvg] := 'mort';
clrscr;
end;
if nomj[x6]= 'mort'
then begin
writeln('choisissez qui emporter avec vous: ');
readln(votechas);
nch:= 0;
repeat
nch:= nch+1
until votechas = nomj[nch];
nomj[nch]:= 'mort';
clrscr;
End
until ((nomj[x1]='mort')and(nomj[x2]='mort')and(nomj[x3]='mort'))
      or((nomj[x4]='mort')and(nomj[x5]='mort')and(nomj[x6]='mort')and(nomj[x7]='mort')and(nomj[x8]='mort'));
If ((nomj[x1]='mort')and(nomj[x2]='mort')and(nomj[x3]='mort'))
then writeln('LES VILLAGEOIS ONT GAGNE')
else if ((nomj[x4]='mort')and(nomj[x5]='mort')and(nomj[x6]='mort')and(nomj[x7]='mort')and(nomj[x8]='mort'))
then writeln('LES LOUPS-GAROUS ONT GAGNE');
end. 
