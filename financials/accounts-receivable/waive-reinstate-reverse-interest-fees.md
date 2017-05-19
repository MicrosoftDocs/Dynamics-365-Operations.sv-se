---
title: "Avstå, återinföra eller återföra ränta"
description: "Det här avsnittet innehåller information om hur du efterskänker, återinför och omvänder kostnader för ränta och avgifter."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59461
ms.assetid: 25ec29f3-e3ea-4abb-bf6b-f6240873b315
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e25a7657c2b859ffd57313ed7eb8da6583e7130d
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="waive-reinstate-or-reverse-interest-fees"></a>Avstå, återinföra eller återföra ränta

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om hur du efterskänker, återinför och omvänder kostnader för ränta och avgifter.

Du kan använda knapparna på **Samla in** fliken på **alla kunder** att avstå, återföra eller återinföra avgifter:

-   Efterskänkta avgifter förlåtas. Du kan avstå från en avgift, om till exempel en kund tvister, och du vill behålla en god affärsrelation med kunden.
-   Återinförda avgifter blir förfallna igen. Du kan återinföra avgifter som avfärdades tidigare. Du kanske måste återinföra avgifter om du bestämmer att de inte borde ha avståtts.
-   Återförda avgifter tas bort från kundens konto och är inte längre aktuellt. Du kan återföra avgifter t.ex. om fel räntesatsen valdes för att beräkna beloppet som en kund är skyldig. Du kan använda en separat process att räkna om ränta och skapa en räntefaktura som innehåller nya avgifter för kunden.

Alla dessa åtgärder som ändrar en räntefaktura. En räntefaktura är en handling som informerar kunder när ränta eller avgifter har påförts kontot. När du efterskänker eller återför ränta eller avgifter, skapas en kreditfaktura eller en justeringsfaktura automatiskt för att kvitta avgifterna. Om du återinföra undantag från avgifter, en faktura som har ett debetbelopp skapas automatiskt för att återinföra de avgifter som kunden är skyldig. Följande tabell beskriver resultaten av varje åtgärd.

| Åtgärd                                                                                                                                                                                                            | Resultat för kunden                                                                                             | Bearbeta                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Avstå från hela räntefakturor tillsammans med alla räntor och avgifter som de omfattar. -eller- Markera och avstå från avgifter eller räntetransaktioner som utgör en del av räntefakturor.                                        | Avgifterna förlåtas.                                                                                           | En kreditfaktura eller justeringsfaktura skapas för kunden. Kreditnotan används för att automatiskt kvitta räntefaktura eller räntetransaktioner eller avgifter som du valt. Den reglerade beloppet är lika med det totala beloppet av avgifter, minus eventuella tidigare betalningar som kunden gjort, och minus eventuellt belopp som tidigare avstått eller avskrivits. Om kreditfakturan överstiger det belopp som kunden är skyldig, kan du konvertera kreditfakturan till en leverantör faktura. Sedan kan du ge kunden en återbetalning.                                                       |
| Återinföra hela räntefakturor tillsammans med alla räntor och avgifter som de omfattar. -eller- Klicka och återinföra avgifter eller räntetransaktioner som utgör en del av räntefakturor.                                | Det rabatterade belopp förfaller igen.                                                                                     | En faktura som har ett debetbelopp skapas och beloppet automatiskt lösas mot avgifter som tidigare avstått från. De verkliga räntefakturorna kommer inte återinföras. I stället skapas en faktura som visar beloppet som förfallit från kunden. De kreditnotor eller justeringsfakturor som skapats för att kvitta avstådda räntefakturor kan fortfarande finnas kvar om de inte används för att kvitta räntefakturor. I detta fall enastående kreditnotor är makulerad. Utestående kreditfakturor, vanligtvis kvittas automatiskt när räntefakturor rabatteras. Det kan dock hända att utestående kreditfaktura finns, om en kund har betalat räntefaktura, även om kunden grälade om avgifterna. |
| Återför hela räntefakturor. -eller- Återför valda räntetransaktioner som utgör en del av en räntefaktura. **Obs!** Du kan inte återföra en avgift. Du kan dock vända hela räntefaktura som omfattar en avgift. | Avgifterna är inte längre förfallna från kunden. Dock kan hända att avgifterna förfaller igen om du räknar om ränta. | Processen är den samma som för avstående av räntefakturor eller valda räntetransaktioner. En kreditfaktura eller justeringsfaktura skapas för kunden. Denna kredit anmärkning används för att automatiskt lösa räntefaktura. Du kan använda en separat process för att beräkna om ränta och skapa en ny räntefaktura.                                                                                                                                                                                                                                                                                                                                                                                              |

> [!NOTE] 
> Du kan också använda en separat process att avskriva skulder. Denna process markerar alla kundtransaktioner för lösning istället för avstående endast avgifter som är en del av räntefakturor.

## <a name="adjust-interest-for-invoices"></a>Justera ränta för fakturor
Förutom att justera räntefakturor kan du ta bort räntekostnader på fakturor med hjälp av en av följande processer. Båda processerna även göra justeringar av tillhörande räntor anteckningar.

### <a name="correct-an-invoice-that-has-associated-interest"></a>Korrigera en faktura som har associerad ränta

Du kan korrigera en bokförd faktura som ingår i en räntefaktura. Denna process kopierar information från befintlig faktura till en ny faktura för att bara göra de korrigeringar som du vill. Fakturan är makulerad och en ny faktura skapas. Ränta på transaktionen återförs även på räntefakturan, om räntefakturan bokfördes. 

Du kan göra korrigeringar med hjälp av **korrekt faktura** på rutan Åtgärd av fri text faktura. Den här knappen är endast tillgänglig om den **fria texten faktura korrigering** " knappen.

### <a name="reverse-a-customer-transaction-that-has-associated-interest"></a>Återför en kundtransaktion som har associerad ränta

Du kan vända en kund transaktion på en faktura om en faktura skapats felaktigt. Om den återförda kundtransaktionen har ränta som ingår i en räntefaktura, och om räntefakturan har konterats, kommer räntan i transaktionen också återföras på räntefakturan. Den räntefaktura avbryts om den inte har bokförts. 

Du kan återföra kundtransaktioner med hjälp av **bakåtknappen**på **kundtransaktioner** sida.

## <a name="waive-or-reinstate-interest-notes"></a>efterskänka eller återinföra räntefakturor
Du kan avstå från eller återinföra alla avgifter på räntefakturor som du väljer. När du avstå från avgifter, det totala beloppet att avstå inte överstiga ett belopp som har ställts in. Du kan bara återinsätta räntefaktura om den inte tidigare avfärdades. 

Du kan avstå från eller återinföra räntefakturor med **räntefaktura** knappen på **Samla in** fliken på **Kund** sidan.

## <a name="waive-or-reinstate-interest-transactions"></a>efterskänka eller återinföra räntetransaktioner
Du kan avstå från eller återinföra specifika räntetransaktioner på en räntefaktura i stället för att justera alla avgifter för räntefakturan. När du avstå från avgifter, det totala beloppet att avstå inte överstiga ett belopp som har ställts in. Du kan bara återinsätta räntetransaktion om den inte tidigare avfärdades. 

Du kan avstå från eller återinföra räntefakturor via **transaktionsränta** knappen på **Samla in** fliken på **Kund** sidan.

## <a name="waive-or-reinstate-fees"></a>efterskänka eller Återinföra avgifter
Du kan avstå från eller återinföra särskilda avgifter på en räntefaktura, i stället för att justera alla avgifter för räntefakturan. När du avstå från avgifter, det totala beloppet att avstå inte överstiga ett belopp som har ställts in. Du kan bara återinsätta en avgift om den avfärdades tidigare. 

Du kan avstå från eller återinföra räntefakturor med**avgift** knappen på **Samla in** fliken på **Kund** sidan.

## <a name="reverse-interest-notes"></a>Återför räntefakturor
Du kan återställa alla avgifter på räntefakturor som du väljer. Återförda avgifter tas bort från kundens konto och är inte längre aktuellt. När räntefakturan har återförts, kan du beräkna om ränta och skapa en ny räntefaktura. 

Du kan återföra räntefakturor med**räntefaktura** knappen på **Samla in** fliken på **Kund** sidan.

## <a name="reverse-interest-transactions"></a>Återför räntetransaktioner
Du kan återställa alla räntetransaktioner som du väljer. Återförda avgifter tas bort från kundens konto och är inte längre aktuellt. När transaktionen har återförts, kan du beräkna om ränta och skapa en ny räntefaktura.

Du kan återföra räntetransaktioner genom **transaktionsränta** knappen på **Samla in** fliken på **sidan Kund** .

## <a name="view-the-history-of-adjustments-for-charges-that-were-waived-reinstated-or-reversed"></a>Visa historiken för justeringar för avgifter som avfärdades, återinsattes eller återfördes
Du kan visa den detaljerade historiken för justeringar, som har gjorts för räntefakturor, till exempel den användare som har skapat justeringen, typ av justering, belopp, och då justeringen angavs. Du kanske till exempel vill visa de tidigare justeringarna som har angetts för en räntefaktura, innan du skapar en ny räntefaktura. 

Du kan återföra räntetransaktioner via **Historik** knappen på **Samla in** fliken på **Kund** sidan.




