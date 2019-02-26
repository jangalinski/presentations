<!-- .slide: data-background="#000000" -->

# CQRS/ES

Was ist das? Warum brauch ich das?

<small>Einhorn Lunch<br/>Jan Galinski<br/>27.02.19</small>

---

## Code is easy
## State is <red>hard</red>

---

# Command
# Query
Responsibility
Segregation
# Event
Sourcing

---

![CQRS Overview](https://heise.cloudimg.io/width/610/q80.png-lossy-80.webp-lossy-80.foil1/_www-heise-de_/developer/imgs/06/9/7/9/0/2/0/abb2-8f91b55dc4f69adb.png)

---

# Commands

--

### Commands (1)

* express an Intent
* Imperative ("Do that!")

--

### Command handler

* handles commands (sic!)
* do not return result
* accept or reject based on known state


---

# Events

--



---

## Links

* [Heise - CQRS neues Architekturprinzip zur Trennung von Befehlen und Abfragen](https://www.heise.de/developer/artikel/CQRS-neues-Architekturprinzip-zur-Trennung-von-Befehlen-und-Abfragen-1797489.html)
