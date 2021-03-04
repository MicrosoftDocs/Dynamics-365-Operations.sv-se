---
title: Registrera materialförbrukning med en mobil enhet
description: Det här avsnittet beskriver ett arbetsflöde som möjliggör registrering av förbrukningen av råmaterial i produktionen med hjälp av en bärbar enhet.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67fbb8eebb637a96638c574373441213c66e9ddc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437949"
---
# <a name="register-material-consumption-using-a-mobile-device"></a>Registrera materialförbrukning med en mobil enhet

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver ett arbetsflöde som möjliggör registrering av förbrukningen av råmaterial i produktionen med hjälp av en bärbar enhet.

<a name="introduction"></a>Introduktion
------------

Arbetsflödet är relevant om det finns strikta krav på att material ska kunna spåras. Om du vill behålla spårbarheten för material måste exakt datum och exakt tid rapporteras för förbrukningen. Den här processen kan ses i motsats till för- eller backflushing-arbete där det finns en avvikelse mellan registreringstiden och tiden då den faktiska förbrukningen sker. Detta förklarar varför en strategi för automatisk förbrukning inte kan inte för vissa material med spårbarhetskrav. Låt oss titta på ett enkelt scenario som beskriver hur du ställer in ett arbetsflöde för att aktivera registrering av förbrukningen av råmaterial med hjälp av en bärbar enhet. [![Skapa ett arbetsflöde för att möjliggöra registrering av förbrukning av råmaterial med en bärbar enhet](./media/scenario3.png)](./media/scenario3.png)

### <a name="scenario-details"></a>Scenario-information

En kontinuerlig produktionsprocess (5) använder batch-kontrollerat råmaterial RM-100. Materialet som finns i lager på lagerstället Bulk-001 (1) vid registreringsskylt PL-1 med två batcher, B1 och B2, båda med en kvantitet på 100 kg. Lagerställearbete (2) publiceras och bearbetas av RM 100 och materialet hämtas från Bulk-001 till platsen för produktionsinleverans PIL-01 (3), som definieras som icke-registreringsskyltkontrollerad. Maskinoperatören väger ut material från platsen för produktionsinleverans (3) och registrerar vikten och batchnumret som förbrukade (4). Från produktionsinleveransplatsen läggs en del av materialet till manuellt i produktionsprocessen i angivna tidsintervall. När maskinoperatören lägger till material, vägs det på en våg och batchnumret registreras.

## <a name="set-up-theworkflow-to-register-consumption-using-a-handheld-device"></a>Konfigurera arbetsflödet för att registrera förbrukning med hjälp av en bärbar enhet
Skapa en färdigvaruprodukt, FG 100, med en strukturlista med material som har batch-styrt råmaterial RM-100. Lägg till två batcher B1 och B2 i RM-100 i en kvantitet på 100 till plats: Bulk-001 vid registreringsskylt: PL-1. Avräkningsprincipen på strukturlisteraden för RM-100 anges till **Manuell**. Ställ in plats för produktionsinleverans på PIL-01. Du kan du göra det genom att välja den här platsen som den standardinleveransplats för lagerställe 51.

1.  Skapa en ny menyartikel för mobila enheter: 

-    **Menyartikelnamn** – Registrera materialförbrukning. 
-    **Rubrik** – Registrera materialförbrukning. 
-    **Läge** – Indirekt. 
-    **Aktivitetskod** – Registrera materialförbrukning.

2.  Lägg till menyartikeln i enhetsmenyn **Mobil produktion**.
3.  Skapa en produktionsorder för den färdiga produkten: 

-    **Artikelnummer** – FG-100 
-    **Plats** – 5 
-    **Lagerställe** – 51 
-    **Kvantitet** – 150

Produktionsordern är **Uppskattad** och **Frisläppt** och lagerarbete har skapats.

4.  Slutför arbetet med hjälp av arbetsflödet för råmaterialplockning för handhållen enhet.

Detta överför materialet från bulkplatsen till produktionsinleveransplatsen PIL-01. När arbetet har slutförts har materialet statusen **Plockas på platsen för produktionsinleverans**. Statusen efter att arbetet har bearbetats kan vara antingen **Plockad** eller **Fysiskt reserverat**. Detta konfigureras med parametern **Utfärda status efter införandet i lagerställeformuläret**.

5.  Starta tillverkningsordern från klienten eller från den handhållna enheten med hjälp av menyartikeln **Produktionsstart**.

När produktionsordern har startat kan du registrera materialförbrukning i arbetsflödet för handenheter. Vi börjar med att registrera förbrukning på 25 kg från batch B1.

6.  Välj menyartikeln  **Registrera material** **förbrukning**. I menyn för handhållen enhet anger du följande information: 

-    Tillverkningsordernumret. 
-    Platsen där materialet ska förbrukas är i det här fallet PIL-01. 
-    Artikelnummer RM-100. 
-    Batchnummer B1. 
-    Kvantitet: 25.

7.  Välj **OK**.

Observera att meddelandet ”Journalrad har skapats” visas på skärmen. På produktionsordern är en öppen journal av typen **Produktionsplocklista** för artikel nummer RM-100 och batch-nummer B1. 

Du kan nu välja att fortsätta med registreringen, till exempel på batchnummer B2. Varje gång du väljer **OK** läggs en ny journalrad till i den öppna journalen. 

När du har slutfört registreringen väljer du **Klart** för att bokföra journalen och avsluta arbetsflödet.

### <a name="additional-comments"></a>Ytterligare kommentarer 

-   Om en användare avbryter arbetsflödet när en journalrad har skapats är journalen i ett ej bokfört tillstånd, men om användaren vid en senare tidpunkt använder arbetsflödet för samma produktionsorder, kommer raderna att läggas till i den öppna journalen i stället för i en ny journal.
-   Det nya arbetsflödet har även stöd för registrering av serienummer.
-   Det går bara att registrera ett artikelnummer som har definierats i strukturlistan eller formeln för vald produktionsorder eller batchorder.
-   Material kan vara överförbrukade. Exempelvis om materialet är beräknat att vara förbrukat med kvantiteten 100 kg kan det sedan vara överförbrukat med samma kvantitet, till exempel 105 kg.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]