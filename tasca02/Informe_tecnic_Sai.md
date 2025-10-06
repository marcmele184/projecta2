![Logo formació professional escola pia sant anna](img/baixa.png)

# Informe tècnic: Estudi i selecció d'un SAI per a TecnoGestió S.L.

**Autor:** Marc Melendo  
**Curs:** 2n B Sistemes Microinformàtics i Xarxes  
**Assignatura:** Seguretat Informàtica  

[Document original al Drive](https://docs.google.com/document/d/1SXR_ajlbw9bHbd_CYLs54Dj5YtFXjRYZ/edit?usp=drive_link&ouid=117080756775083118180&rtpof=true&sd=true)

---

## **Índex**

1. [Introducció](#1-introducció)  
2. [Inventari d'equips](#2-inventari-dequips)  
3. [Càlcul de potència total](#3-càlcul-de-potència-total)  
4. [Determinació de l'autonomia necessària](#4-determinació-de-lautonomia-necessària)  
5. [Recerca de models de SAI](#5-recerca-de-models-de-sai)  
6. [Anàlisi comparativa i selecció final](#6-anàlisi-comparativa-i-selecció-final)

---

## 1. Introducció

> L'objectiu d'aquest informe és determinar les necessitats d'un SAI (Sistema d’Alimentació Ininterrompuda) per solucionar les constants incidències amb el subministrament elèctric a la zona on es troba la instal·lació de TecnoGestió S.L.

---

## 2. Inventari d'equips

| Dispositiu               | Quantitat | Consum individual (W/VA) | Consum total (W/VA) |
|--------------------------|------------|---------------------------|----------------------|
| Ordinador de sobretaula  | 4          | 410W / 585VA              | 1640W / 2340VA       |
| Monitor                  | 4          | 39W / 55VA                | 156W / 220VA         |
| Router                   | 1          | 28W / 39VA                | 28W / 39VA           |
| **Total**                | —          | —                         | **1824W / 2599VA**   |

> La impressora-fotocopiadora multifunció **no es connectarà** al SAI, ja que l’objectiu principal és mantenir els ordinadors amb energia suficient per desar la feina abans d’una possible pèrdua de corrent.

---

## 3. Càlcul de potència total

> Per escollir el SAI adequat s’han de sumar tots els consums per obtenir el consum total:
>
> **Total:** 1824W / 2599VA  
> Afegint un marge del **20%** per evitar treballar sempre al màxim i preveure futures ampliacions:
>
> **Resultat final:** **2189W / 3119VA**

---

## 4. Determinació de l'autonomia necessària

> L’empresa demana un mínim de **10 minuts d’autonomia** per poder desar la feina en cas d’apagada.
>
> **Fórmula:**
>
> ```
> T = (Capacitat bateries × Eficiència / Potència VA) × 60
> ```
>
> Per calcular la capacitat de la bateria necessària:
>
> ```
> Capacitat = ((Temps × Potència) / Eficiència) / 60
> ```
>
> Si considerem:
>
> - SAI de **4000VA** → Capacitat necessària ≈ **952,39 Ah**
> - SAI de **7500VA** → Capacitat necessària ≈ **1.785,72 Ah**

---

## 5. Recerca de models de SAI

| Model                   | Potència màxima (VA / W) | Autonomia estimada | Sortides | Tecnologia |
|--------------------------|---------------------------|--------------------|-----------|-------------|
| **SLC-4000-TWIN PRO3**  | 4000 VA / 4000 W          | ~11 min al 80% de càrrega amb bateries internes; ampliable fins a 44–88 min amb mòduls externs | *C13*, *C19* | On-line, doble conversió, monofàsic, DSP, FP=1 |
| **SLC-4000-TWIN RT3**   | 4000 VA / 4000 W          | Depèn de la configuració | *C13* | On-line, doble conversió, monofàsic, torre/rack, FP=1 |
| **SLC-7,5-CUBE4**       | 7500 VA / 7500 W (trifàsic) | Ampliable amb bancs externs de bateries | No especificat | On-line, doble conversió, trifàsic, DSP, FP=1 |

---

## 6. Anàlisi comparativa i selecció final

> La selecció final del SAI dependrà de les necessitats de l’empresa:
>
> - Si es preveu **creixement futur** i es vol capacitat sobrant → **SLC-7,5-CUBE4**  
> - Si es busca **estalvi i eficiència**, amb opció d’ampliació de bateries → **SLC-4000-TWIN PRO3**  
> - Si es vol **format convertible torre/rack** i flexibilitat → **SLC-4000-TWIN RT3**
>
> En tots els casos, és recomanable afegir **mòduls de bateria externs** per garantir l’autonomia mínima requerida.

---





[Tornar a enunciat](readme.md)
