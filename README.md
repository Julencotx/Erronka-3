# Erronka-3

**_SARRERA:_** 
Erronka honetan, FPGAk erabiliz joku digitalak egin behar dira. Horretarako gailu konbinazionalak eta sekuentzialak erabiliko ditugu.
Gure kasuan Push Up jokua egingo dugu FPGA-ari buruz ikasteko, joku honetan, antolatzaile batek pultsadore bati emanda, argi bat piztuko du eta (gutxienez) beste bi jokalariek, pultsadore bat eman beharko diote ahalik eta arinen. Pultsadoreari arinen ematen dion jokalariak puntu bat lortuko du. 
Erronka honetan, Alhambra II plakatxoarekin batera, ICEStudio eta MultiSim programak erabiliko ditugu, erronka hau aurrera eramateko.

_**GARAPENA:**_
**2.1-Ate logikoak:**
Lehenik eta behin erronka hasi baino arinago elektronika digitala ikasi genuen, honekin batera ate logikoak erabiltzen eta hauen funtzionamendua ikasi dugu, erronka aurrera atera ahal izateko, gure erronkan oso garrantzitsuak izan dira zeren eta, gure jokua funtziona dezan hainbat kondizio bete behar ziren aldi berean, adb;
Display-an puntu bat gehitzeko, jokalariaren pultsadora sakatu behar zen, baina honekin batera, antolatzailearen LED argia pizturik egon behar zen, kasu honetan adibidez AND bat erabiltzen da.
Hauek izan dira erabili ditugun ate logiko nagusienak:

          **2.1.1-NOT:** 
NOT ate logikoa, ezeztapen logikoa inplementatzen duen zirkuitoa da, hau da, sarrera “1” denean irteera balioa “0” izango du eta sarrera “1” denean irteera “0” izango da.
![NOT data](https://github.com/Julencotx/Erronka-3/assets/151912632/e0b2017b-67f6-4423-bc75-ccfef3429f3f)



          **2.1.2-AND:**  
AND ate logikoa funtzionarazteko, sarrera guztiek “1” balioa izan behar dute, bestela, irteerak “0” balioa izango dute.
![AND data](https://github.com/Julencotx/Erronka-3/assets/151912632/6d1ad799-84d5-471a-bc7a-fd537e5d46b0)


          **2.1.3-OR:**
OR ate logikoak, AND-ak ezbezala, nahiakoa da sarrera bati “1” ematea, irteerako seinalea aldatzeko.
![OR data](https://github.com/Julencotx/Erronka-3/assets/151912632/40f389aa-2db7-4ff4-bf64-18e6a320760f)



**2.2-Erabilitako gailuak:**
Ondoren, gailu logikoak erabili ditugu bai zirkuitu konbinazionalak eta sekuentzialak ikasis eta hauetan erabiltzen ditugun elementuak behatuz, erabili ditugunak hurrengoak izan dira.

          **2.2.1-Dekodifikadora:**
Dekodifikadora, zirkuitu konbanazional bat da, non X sarrera eta Y irteera ditu, kodifikadoraren alderantzizkoa da, hau da, hizkuntza binarioan dagoen informazioa ateratzen du. Honela sarrerak X bit-eko konbinazio binarioan aktibatzean, irteera aktibatzen da, eta aplikatutako binarioan dagoen informazioa isladatuz. Gure proiektuan, display-an zenbakiak agertzeko erabiltzen dugu, honen konexioak display-aren sarrerekin konektatuta doaz.
![Dekodifikadora](https://github.com/Julencotx/Erronka-3/assets/151912632/ec70959c-5633-43fe-9ee2-12d539a9daec)




          **2.2.2-Kontadora:** 
Hainbat kontadore mota daude, asinkrono (gorazkoa, beheranzkoa eta mixtoa), beste askoren artean, guk erabili dugun kontadora, Kontador asinkrono mixtoa da.
Kontadore asinkrono mixtoa, izenak dioen bezala, gorazko eta beheranzko-aren arteko nahasketa da baina beste lerro bat erabiliz “UP/DOWN” deritzona, honekin seinalea “1” denean kontadora gorantza egiten du eta “0” denenan berantza.
![Kontadora](https://github.com/Julencotx/Erronka-3/assets/151912632/74b41d10-d5d0-494f-99b6-73796784a699)


          **2.2.3-RS biegongorra:**
Multibibradore honetan, aldagai berri bat agertzen da, hau denbora da, honen arabera sarrerek aurreko irteeren balore berdina hartzen du. Biegonkor honek, bi sarrera izanda, denbora ere sarrera moduan hatzen da kontuan, hau Qt deitzen da, honek aurreko deboran duen balioa neurtzen du. Irteera moduan Qt+1 honek Qt sarrerak duen baloreari egiten dio erreferentzia hau konmutatu ostean eta Qt balioak, Q irteerari egiten dio erreferentzia NOT-a konmutatu baino lehen.
![RS](https://github.com/Julencotx/Erronka-3/assets/151912632/fd14d9e5-e110-40ef-b5d8-32b7b48f98a9)







          **2.2.4-Antirrebotesa:**
Kontaktuzko elementuetan (pultsagailuetan adibidez) akzio mekanikozko elementuak izanik, reboteak gerta daitezke. Inpulso honek, kontaktuaren akzionamenduak eraginda sortzen direnak, bizkorrak izaten dira baina, zirkuitu mota batzuetan, arazoak erakar ditzakez. Gure proiektuan, antirrebotesa ez badugu jartzen, pultsadorari emandakoan, puntu bat baino gehiago lortuko genituzke, antirrebotesaren eskema honetan bi elementu adierazgarri ikus ditzakeguz.
![Antirrebotes](https://github.com/Julencotx/Erronka-3/assets/151912632/0ad64b34-119f-4fde-bdc3-2ad2a353ff62)


Trigger Schmitt: 
Trigger Schmitt honek, 1,5V-ra heltzean, sistemak “0” moduan hartuko du eta eta berriro 3,5V-tatik igarotzean, “1” moduan. Hauen artean, aurreko balioa balioa hartuko du.
![Trigger](https://github.com/Julencotx/Erronka-3/assets/151912632/f91f3e29-dca5-47d6-b6be-ab62ecdb4e16)
![VOLT](https://github.com/Julencotx/Erronka-3/assets/151912632/1552de8e-ab0f-4319-8cb7-7f54b247c08a)





Kondensadora: 
Kondentsadora, energia elektrikoa metatzen duen gailu elektronikoa da. Bi gainazalez osatzen dira, material dielektriko batez bereizirik (airea adibidez). Gainazal eroaleei potentzial-diferentzia bat aplikatzen zaienean, elektrikoki kargatzen dira. 
Aurreko bi konpenenteen arteko batuketak, pultsagailua akzionatzean agertzen diren              errebotean neutralizatenz dituzte sisteman arazorik sor ez dezaten.
![Kondensador](https://github.com/Julencotx/Erronka-3/assets/151912632/6e42fc29-fd42-45fa-a5f8-27fb0053a316)



          **2.2.5-7 Segmentuko display-a:**
Karaktereak ekipo elektronikoetan irudikatzeko modu bat da. Banaka piztu edo itzali daitezkeen zazpi segmentuk osatzen dute; Adibidez,
Segmentu guztiak aktibatzen edo pizten badira, "8" zenbakia sortuko da.
"a, b, c, d, e, f" segmentuak bakarrik aktibatzen badira, "0" zenbakia sortzen da.
Segmentuak bakarrik aktibatzen badira: "a, b, g, e, d", "2" zenbakia sortzen da.
Segmentuak bakarrik aktibatzen badira: "b, c, f, g", "4" zenbakia sortzen da.
Gure kasuan, display-a anodo komun-ekoa da, hau da, anodoak puntu berdinerakonektatuta daude, eta hauek “0”
![3 0_1024x1024](https://github.com/Julencotx/Erronka-3/assets/151912632/0fcc8b5e-0254-46e7-9a4c-acb5870db363)


**2.3-MultiSim-eko eskema:**
Behin erabiliko ditugun materialak ikusita eta aztertuta MultiSim ean eskemak egiten hasi ginen, MultiSim eskema ugari egin genituen, lehenik eta behin eskema osos bat egin genuen, aurreko gaietan ikusitako ate logiko eta elementu logikoak ikusita:
![DESORDEN](https://github.com/Julencotx/Erronka-3/assets/151912632/01021870-8d39-4d72-a7e0-d196704c5b62)

Ikusten denez nahiko desordenatuta zegoen, hori dela eta beste bertsio bat egin genuen ordenatuago dagoena horrela simulazioa ondo egiten zuen baina ez zuen guri eskatzen zaiguna egiten:
![MultiSim eskema](https://github.com/Julencotx/Erronka-3/assets/151912632/c0270ba4-ec92-43b8-ae63-a09f71674ffb)

Gure arazoak konpontzeko, berriro ere ordenatu genuen eskema osoa, jokalari bakoitza alde batean utzi genuen arazoak hobeto ikusteko. Gure arazorik nagusiena UP eta DOWN efektuak aldi berean egiten zuena da, hau da, puntuazioa gehitu beharrean,  gehitu eta kendu egiten zuen aldi berean. Hori konpontzeko, estatu makinak erabili behar izan genituen.
<img width="443" alt="Captura de pantalla 2023-11-26 224503 (2)" src="https://github.com/Julencotx/Erronka-3/assets/151912632/527ffcc8-24dd-4f55-a0e9-a77fdc0dc4fc">

**2.4-ICEStudio programa:**
MultiSim-en eskema egiten hari ginen bitartean, ICEStudion programa egin genuen, ondoren hau FPGA plakan (Alhambra II) kargatzeko eta programa funtzionatzan jartzeko ProtoBoard-ean, ICEStudio programa gutxiago egin genituen zeren eta aktualizatu egiten genuen aurreko bertsioa, horietako betsioa hau da:
![ICEStudio programa](https://github.com/Julencotx/Erronka-3/assets/151912632/e8178bc7-22e4-43d3-94f0-d1c3c2e03c08)

Ondoren gai gehiago jarri genizkion programari eta pixkat ordenatu genuen hobeto ulertzeko:
![PROGRAMA](https://github.com/Julencotx/Erronka-3/assets/151912632/d0da8f2d-b766-4f62-956c-4d18755e99a8)


**2.5-Muntaia:**
Azkenik, muntaia egin genuen, jokuaren funtzionamendu finala ikusteko eta jokua praktikan jartzeko, herabili genituen materialak hauek izan ziren:

- Pultsadorak: 3 Unitate
- LED ak: 3 Unitate
- Display-ak: 2 Unitate
- Buzzer-a: 1 Unitate
- Erresistentziak 220Ω: 15 Unitate
- Erresistentziak 1kΩ: 4 Unitate
- Alhambra II plaka: 1 Unitate
- ProtoBoard-a: 1 Unitate
![Muntaia](https://github.com/Julencotx/Erronka-3/assets/151912632/8defe6b4-a506-41f9-9e96-c2654d96e76e)
