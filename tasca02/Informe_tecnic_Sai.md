---
title: |
  []{#_4e6abd93t3fi
  .anchor}![](media/image1.png){width="4.682292213473316in"
  height="4.682292213473316in"}

  []{#_nwjmca5ygnq5 .anchor}

  []{#_lsil67wj6rsr .anchor}

  []{#_s967ew28qdlb .anchor}

  []{#_9s7wa13pa9p9 .anchor}

  []{#_oswlkok0886e .anchor}

  []{#_t1m69z2qaf5n .anchor}

  []{#_4inp21ajg8e .anchor}

  []{#_8ckvqdkqklyy .anchor}Informe tècnic: Estudi i selecció d'un SAI
  per a TecnoGestió S.L.
---

Marc Melendo

2n b sistemes microinformàtics i xarxes

Seguretat informàtica

[[Drive]{.underline}](https://docs.google.com/document/d/1SXR_ajlbw9bHbd_CYLs54Dj5YtFXjRYZ/edit?usp=drive_link&ouid=117080756775083118180&rtpof=true&sd=true)

## **Index **

[**1. Introducció 3**](#introducció)

[**2. Inventari d'equips 3**](#inventari-dequips)

[**3. Càlcul de potència total 3**](#càlcul-de-potència-total)

[**4. Determinació de l'autonomia necessària
4**](#determinació-de-lautonomia-necessària)

[**5. Recerca de models de SAI 5**](#recerca-de-models-de-sai)

[**6. Anàlisi comparativa i selecció final
5**](#anàlisi-comparativa-i-selecció-final)

##  

## 

# 1. Introducció

> L'objectiu d'aquest informe és proporcionar un informe per poder veure
> quines son les necessitats a cubrir d'un sai per poder solucionar el
> problema de les constants incidències amb el subministrament elèctric
> a la zona que té una instal·lació que és demostra a continuació

# 2. Inventari d'equips

  --------------------------------------------------------------------------
  Dispositiu        Quantitat   Consum individual      Consum total (W/VA)
                                (W/VA)                 
  ----------------- ----------- ---------------------- ---------------------
  Ordinador de      4           410W/585VA             1640W/2340VA
  sobretaula                                           

  Monitors          4           39W/55VA               156W/220VA

  Router            1           28W/39VA               28W/39VA
  --------------------------------------------------------------------------

En aquest cas la impressora-fotocopiadora multifunció no la tindrem
conectada al sai ja que el objectiu principal del sai és mantenir els
ordinadors amb energia per poder guardar la feina abans de perdre-la

# 3. Càlcul de potència total

> Per poder escollir la millor opció per el sai s\'haurà de sumar tots
> els consums per poder aconseguir el consum total en aquest cas sera
> de:
>
> 1824W/2599VA afegint el 20% de marge per aconseguir que el sai no
> treballi sempre a las máximas capacitats o per futures ampliacions el
> resultat sera de: 2189W/3.119VA

##  

# 4. Determinació de l'autonomia necessària

> En aquest cas l'empresa ens demana un mínim de 10 minuts per poder
> guardar la feina, per poder calcular la bateria necessària per poder
> tindre tots els dispositius necessaris
>
> La fórmula necessària per calcular això és la següent:
>
> T=(capacitat bateries · Eficiència/Pot. VA) ·60
>
> Per tant jo en el meu cas he seleccionat 3 tipos de sais que tenen una
> potencia de 4000V i 7500V
>
> Per calcular la capacitat de la bateria farem servir la següent
> formula
>
> Capacitat de les bateries = ((Temps · Potencia) / Eficiència) / 60
>
> En el cas de que el sai tingui 4000VA de potencia la bateria haurà de
> tindre una capacitat de 952,39 Ah i en cas de 7500VA la capacitat de
> la batería será de 1.785,72 Ah

#  

# 5. Recerca de models de SAI

## 

## 

+-------------+-------------+-------------+-------------+-------------+
| #           | ## **Potè   | ##          | ## **Nombre | ## **T      |
| # **Model** | ncia màxima | **Autonomia |  i tipus de | ecnologia** |
|             |  (VA / W)** |  estimada** |  sortides** |             |
+=============+=============+=============+=============+=============+
| ##          | ## 4000     | ## \~11 min | ## So       | ## On-line, |
| **SLC-4000- | VA / 4000 W |  al 80 % de | rtides AC t |  doble conv |
| TWIN PRO3** |             |  càrrega am | ipus **C13* | ersió, mono |
|             |             | b bateries  | * i **C19** | fàsic, amb  |
|             |             | internes; a |             | tecnologia  |
|             |             | mpliable fi |             | DSP, FP = 1 |
|             |             | ns a 44-88  |             |             |
|             |             | min amb mòd |             |             |
|             |             | uls externs |             |             |
+-------------+-------------+-------------+-------------+-------------+
| ##          | ## 4000     | ## No esp   | ## 2 sor    | ## On-line, |
|  **SLC-4000 | VA / 4000 W | ecificada ( | tides AC ti |  doble conv |
| -TWIN RT3** |             | depèn de co | pus **C13** | ersió, mono |
|             |             | nfiguració) |             | fàsic, form |
|             |             |             |             | at torre/ra |
|             |             |             |             | ck converti |
|             |             |             |             | ble, FP = 1 |
+-------------+-------------+-------------+-------------+-------------+
| ## **SLC-   | ## 7500     | ## No espe  | ## No espe  | ## On-l     |
| 7,5-CUBE4** | VA / 7500 W | cificada; a | cificat al  | ine, doble  |
|             |  (trifàsic) | mb opcions  | full públic | conversió,  |
|             |             | d'autonomia |             | trifàsic, c |
|             |             |  estesa mit |             | ontrol DSP, |
|             |             | jançant ban |             |  HF, FP = 1 |
|             |             | cs de bater |             |             |
|             |             | ies externs |             |             |
+-------------+-------------+-------------+-------------+-------------+

# 6. Anàlisi comparativa i selecció final

> Per poder escollir el sai final que vols a la teva empresa dependrà de
> varis factors els principals seran si vols creixement sense preocupar
> se per el sai escolliria el CUBE4 si el que vols és estalviar seria el
> SLC-4000-TWIN PRO3 peró s'ha de tenir en compte que faria falta mòduls
> de bateria i si vols un format convertible el RT3 és la millor opció
> però també faria falta també mòduls de bateria extern.
