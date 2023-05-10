# atividade-banco-de-dados-OSCAR-


Atividades para trabalhar com o Oscar
1- Quantas vezes Natalie Portman foi indicada ao Oscar?

2- Quantos Oscars Natalie Portman ganhou?

3- Amy Adams já ganhou algum Oscar?

4- A série de filmes Toy Story ganhou um Oscar em quais anos?

5- Quem tem mais Oscars: a categoria "Melhor Ator" ou "Melhor Filme"?

6- O primeiro Oscar para melhor Atriz foi para quem? Em que ano?

7- Na coluna/campo Winner, altere todos os valores com "True" para 1 e todos os valores "False" para 0.

8- Em qual edição do Oscar "Crash" ganhou o prêmio principal?

9- Bom... dê um Oscar para um filme que merece muito, mas não ganhou.

10- O filme Central do Brasil aparece no Oscar?

11- Inclua no banco 3 filmes que nunca nem foram nomeados ao Oscar, mas que na sua opinião, merecem. 

12- Crie uma nova categoria de premiação. Qualquer prêmio que você queira dar. Agora vamos dar esses prêmios aos filmes que você cadastrou na questão acima.

13- Qual foi o primeiro ano a ter um prêmio do Oscar?

14 - Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor?

15- Agora procure 7 atrizes que não sejam americanas, europeias ou brasileiras.  Vamos cadastrá-los no nosso banco, mas eles ainda não ganharam o Oscar. Só foram nomeados.

16- Agora vamos falar da sua vida. Me diga o nome de uma pessoa que você admira e o que ela fez na sua vida. Agora me diz: Quê prêmio essa pessoa merece? 



(MySQL Workbench)

-- quantas vezes natalie portman foi indicada ao oscar?
-- foi indicada 3 vezes.
select * from movies where name= "natalie portman";

-- quantos oscars natalie portman ganhou?
--  ganhou 1 vez.
select * from movies where name = "natalie portman" and winner= "true";

-- amy adams já ganhou algum oscar?
-- não.
select * from movies where name = "amy adams" and winner = "true";

-- toy story 3 ganhou um oscar em quais anos?
-- ganhou 1 oscar na categoria "animated feature film" e 1 oscar na categoria "music (original song)".
select * from movies where film = "toy story 3";

-- quem tem mais oscars: a categoria "melhor ator" ou "melhor filme"?
-- categoria "melhor ator" tem 49 oscars e categoria "melhor filme" tem 58 oscars.
select count(*) as oscars_melhor_ator from movies where category = "actor"  and winner = "1";
select count(*) as oscars_melhor_filme  from movies where category = "best picture" and winner = "1";

-- na coluna/campo winner, altere todos os valores com "true" para 1 e todos os valores "false" para 0.
update movies set winner = "0" where winner = "false";
update movies set winner = "1" where winner = "true";

-- em qual edição do oscar "crash" ganhou o prêmio principal?
-- ganhou na edição 78.
select * from movies where film = "crash";

--  bom... dê um oscar para um filme que merece muito, mas não ganhou.
update movies set winner = "1" where film = "the noose";

-- o filme central do brasil aparece no oscar?
-- não
select * from movies where film = "central do brasil";

-- inclua no banco 3 filmes que nunca nem foram nomeados ao oscar, mas que na sua opinião, merecem. 

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2014, 2015, 87, 'best picture', 'the grand budapest hotel', 'o grande hotel budapeste', '0');
insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2011, 2012, 84, 'best picture', 'drive', 'drive', '0');
insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2013, 2014, 86, 'best picture', 'inside llewyn davis', 'inside llewyn davis - balada de um homem comum', '0');

--  crie uma nova categoria de premiação. qualquer prêmio que você queira dar. 
-- agora vamos dar esses prêmios aos filmes que você cadastrou na questão acima.
update movies set category = 'best production design' where film = 'o grande hotel budapeste';
update movies set category = 'best production design' where film = 'drive';
update movies set category = 'best production design' where film = 'inside llewyn davis - balada de um homem comum';

-- qual foi o primeiro ano a ter um prêmio do oscar?
-- ano de 1928.
select * from movies where winner = '1' order by ceremony asc ;

-- pensando no ano em que você nasceu: qual foi o oscar de melhor filme, melhor atriz e melhor diretor?
-- a única categoria que ganhou foi melhor diretor:"art direction:  john myhre; set decoration:  gordon sim".
select * from movies where year_ceremony  = "2003" and winner = "0" and category = "actor";
select * from movies where year_ceremony  = "2003" and winner = "0" and category = "actress";
select * from movies where year_ceremony  = "2003" and winner = "1" and category = "art direction";

--  agora procure 7 atrizes que não sejam americanas, europeias ou brasileiras.  
-- vamos cadastrá-los no nosso banco, mas eles ainda não ganharam o oscar. só foram nomeados.

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2003, 2004, 76, 'best supporting actress', 'shohreh aghdashloo', 'house of sand and fog', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2006, 2007, 79, 'best supporting actress', 'rinko kikuchi', 'babel', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2004, 2005, 77, 'best actress', 'catalina sandino moreno', 'maria full of grace', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2018, 2019, 91, 'best actress', 'yalitza aparicio', 'roma', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2011, 2012, 84, 'best supporting actress', 'bérénice bejo', 'the artist', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2008, 2009, 81, 'best supporting actress', 'viola davis', 'doubt', '0');

insert into movies (year_film, year_ceremony, ceremony, category, name, film, winner)
values (2002, 2003, 75, 'best actress', 'salma hayek', 'frida', '0');

-- agora vamos falar da sua vida. 
-- me diga o nome de uma pessoa que você admira e o que ela fez na sua vida. 
-- agora me diz: quê prêmio essa pessoa merece? 




































