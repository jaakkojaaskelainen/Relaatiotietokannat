# 03 - Yhteen tauluun kohdistuvien kyselyiden harjoitukset


### Tehtävä 1

```sql
select * from goal;
```

![Tehtävä 1](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/07e244f9378ad73caab4564c06bd109d9c109ab0/03_Tehta%CC%88va%CC%88%20_1.png)

### Tehtävä 2

```sql
select name, type from airport where iso_country = "FI";
```

![Tehtävä 2](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/03_Tehta%CC%88va%CC%88_2.png)

### Tehtävä 3

```sql
select name from airport where iso_country = "FI" order by name;
```

![Tehtävä 3](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/03_Tehta%CC%88va%CC%88_3.png)

### Tehtävä 4

```sql
select name, type from airport where iso_country = "FI" order by type, name;
```

![Tehtävä 4](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/03_Tehta%CC%88va%CC%88_4.png)

### Tehtävä 5

```sql
select name from country where name like "F%";
```

![Tehtävä 5](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/03_Tehta%CC%88va%CC%88_5.png)

### Tehtävä 6

```sql
select name from country where name like "%F%";
```

![Tehtävä 6](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/03_Tehta%CC%88va%CC%88_6.png)

### Tehtävä 7

```sql
select location from game where screen_name = "Vesa";
```

![Tehtävä 7](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/03_Tehta%CC%88va%CC%88_7.png)

### Tehtävä 8

```sql
select co2_consumed from game where screen_name = "Ilkka";
```

![Tehtävä 8](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/03_Tehta%CC%88va%CC%88_8.png)

### Tehtävä 9

```sql
select distinct co2_budget from game;
```

![Tehtävä 9](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/03_Tehta%CC%88va%CC%88_9.png)


# 04 - Where-osan liitosehto harjoitukset


### Tehtävä 1

```sql
select name as "country name" , type as "airport name" from airport where iso_country = "IS";
```

![Tehtävä 1](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/04_Tehta%CC%88va%CC%88_1.png)

### Tehtävä 2

```sql
select name as "airport name", type from airport where type like "large_airport" and iso_country = "FR";
```

![Tehtävä 2](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/04_Tehta%CC%88va%CC%88_2.png)

### Tehtävä 3

```sql
select country.name as "country name", airport.name as "airport name"
from airport, country
where airport.iso_country = country.iso_country and country.continent = "AN";
```

![Tehtävä 3](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/04_Tehta%CC%88va%CC%88_3.png)

### Tehtävä 4

```sql
select elevation_ft 
from airport, game 
where location = ident and screen_name = "Heini";
```

![Tehtävä 4](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/04_Tehta%CC%88va%CC%88_4.png)

### Tehtävä 5

```sql
select elevation_ft * 0.3048 as elevation_m
from airport, game
where location = ident and screen_name = "Heini";
```

![Tehtävä 5](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/04_Tehta%CC%88va%CC%88_5.png)

### Tehtävä 6

```sql
select airport.name
from airport, game
where location = ident and screen_name = "Ilkka";
```

![Tehtävä 6](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/04_Tehta%CC%88va%CC%88_6.png)

### Tehtävä 7

```sql
select country.name
from airport, game, country
where location = ident and airport.iso_country = country.iso_country  and screen_name = "Ilkka";
```

![Tehtävä 7](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/04_Tehta%CC%88va%CC%88_7.png)

### Tehtävä 8

```sql
select name
from goal, goal_reached, game
where game.id = game_id and goal.id = goal_id and screen_name = "Heini";
```

![Tehtävä 8](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/04_Tehta%CC%88va%CC%88_8.png)

### Tehtävä 9

```sql
select airport.name
from airport, game, goal, goal_reached
where ident = location and game.id = game_id and goal.id = goal_id and goal.name = "CLOUDS" and screen_name = "Ilkka";
```

![Tehtävä 9](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/04_Tehta%CC%88va%CC%88_9.png)

### Tehtävä 10

```sql
select country.name
from country, airport, game, goal, goal_reached
where airport.iso_country = country.iso_country and ident = location and game.id = game_id and goal.id = goal_id and screen_name = "Ilkka" and goal.name = "CLOUDS";
```

![Tehtävä 10](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/04_Tehta%CC%88va%CC%88_10.png)

# 05 - Join harjoitukset

### Tehtävä 1

```sql
select country.name as "country name", airport.name as "airport name"
from country inner join airport on airport.iso_country = country.iso_country
where country.name = "Finland" and scheduled_service = "yes";
```

![Tehtävä 1](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/05_Tehta%CC%88va%CC%88_1.png)

### Tehtävä 2

```sql
select screen_name, airport.name
from game inner join airport on location = ident;
```

![Tehtävä 2](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/05_Tehta%CC%88va%CC%88_2.png)

### Tehtävä 3

```sql
select screen_name, country.name
from game inner join airport on location = ident inner join country on airport.iso_country = country.iso_country;
```

![Tehtävä 3](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/05_Tehta%CC%88va%CC%88_3.png)

### Tehtävä 4

```sql
select airport.name, screen_name
from airport left join game on ident = location where name like "%Hels%";
```

![Tehtävä 4](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/05_Tehta%CC%88va%CC%88_4.png)

### Tehtävä 5

```sql
select name, screen_name
from goal left join goal_reached on goal.id = goal_id left join game on game.id = game_id;
```

![Tehtävä 5](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/05_Tehta%CC%88va%CC%88_5.png)

# 06 - Sisäkysely harjoitukset

### Tehtävä 1

```sql
select name
from country
where iso_country in(
select iso_country
from airport
where name like "Satsuma%"
);
```

![Tehtävä 1](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/06_Tehta%CC%88va%CC%88_1.png)

### Tehtävä 2

```sql
select name
from airport
where iso_country in(
select iso_country
from airport
where iso_country = "MC"
);
```

![Tehtävä 2](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/06_Tehta%CC%88va%CC%88_2.png)

### Tehtävä 3

```sql
select screen_name
from game
where id in (
select game_id
from goal_reached
where goal_id in(
select id
from goal
where name = "CLOUDS"
)
);
```

![Tehtävä 3](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/06_Tehta%CC%88va%CC%88_3.png)

### Tehtävä 4

```sql
select country.name
from country
where iso_country not in (
select airport.iso_country
from airport
);
```

![Tehtävä 4](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/06_Tehta%CC%88va%CC%88_4.png)

### Tehtävä 5

```sql
select goal.name
from goal
where id not in (
select goal.id
from goal, goal_reached, game
where game.id=game.id and goal.id=goal_id and screen_name="Heini"
);
```

![Tehtävä 5](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/06_Tehta%CC%88va%CC%88_5.png)

# 07 - Koostetieto kyselyt harjoitukset

### Tehtävä 1

```sql
select max(elevation_ft)
from airport;
```

![Tehtävä 1](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/07_Tehta%CC%88va%CC%88_1.png)

### Tehtävä 2

```sql
select continent, count(*)
from country
group by continent;
```

![Tehtävä 2](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/07_Tehta%CC%88va%CC%88_2.png)

### Tehtävä 3

```sql
select screen_name, count(*)
from game, goal_reached
where id = game_id
group by screen_name;
```

![Tehtävä 3](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/07_Tehta%CC%88va%CC%88_3.png)

### Tehtävä 4

```sql
select screen_name
from game
where co2_consumed in (
select min(co2_consumed)
from game)
;
```

![Tehtävä 4](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/07_Tehta%CC%88va%CC%88_4.png)

### Tehtävä 5

```sql
select country.name, count(*)
from airport, country
where airport.iso_country = country.iso_country
group by country.iso_country
order by count(*) desc
limit 50;
```

![Tehtävä 5](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/07_Tehta%CC%88va%CC%88_5.png)

### Tehtävä 6

```sql
select country.name
from airport, country
where airport.iso_country = country.iso_country
group by country.iso_country
having count(*) > 1000;
```

![Tehtävä 6](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/07_Tehta%CC%88va%CC%88_6.png)

### Tehtävä 7

```sql
select airport.name
from airport
where elevation_ft in (
select max(elevation_ft)
from airport)
;
```

![Tehtävä 7](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/07_Tehta%CC%88va%CC%88_7.png)

### Tehtävä 8

```sql
select country.name
from country
where iso_country in (
select iso_country
from airport
where elevation_ft in (
select max(elevation_ft)
from airport)
);
```

![Tehtävä 8](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/07_Tehta%CC%88va%CC%88_8.png)

### Tehtävä 9

```sql
select count(*)
from game, goal_reached
where id = game_id and screen_name = "Vesa"
group by screen_name;
```

![Tehtävä 9](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/07_Tehta%CC%88va%CC%88_9.png)

### Tehtävä 10

```sql
select airport.name
from airport
where latitude_deg in(
select min(latitude_deg)
from airport
);
```

![Tehtävä 10](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/07_Tehta%CC%88va%CC%88_10.png)

# 08 - Päivityskyselyt harjoitukset

### Tehtävä 1

```sql
update game
set location = (select ident from airport where name = "Nottingham Airport"), co2_consumed = co2_consumed+500
where screen_name = "Vesa";
```

![Tehtävä 1](https://github.com/jaakkojaaskelainen/Relaatiotietokannat/blob/070efbeeea9733fc07f7330781a57bcc15b035cc/08_Tehta%CC%88va%CC%88_1.png)











