---
title: Skapa en Excel-arbetsbok för att redigera butikstransaktioner
description: Det här ämnet beskriver hur du skapar en Excel-arbetsbok för att redigera butikstransaktioner i Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3a4bc0a91ee2215dcde2f18575d58ab1ef2f5581
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207953"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a>Skapa en Excel-arbetsbok för att redigera butikstransaktioner

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver hur du skapar en Excel-arbetsbok för att redigera butikstransaktioner i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Det finns en fördefinierad Excel-mall som kunder kan komma åt från olika delar av systemet och använda för att redigera och granska butikstransaktioner. För detta ändamål går det dock också att skapa en anpassad Excel-arbetsbok.

## <a name="create-and-configure-an-excel-workbook"></a>Skapa och konfigurera en Excel-arbetsbok

Följ de här stegen om du vill skapa och konfigurera en Excel-arbetsbok så att du kan redigera butikstransaktioner.

1. Öppna Excel och skapa en tom arbetsbok.
1. Välj **Mina tillägg** på fliken **Infoga**.
1. Välj länken **Lägg till serverinformation** i det högra fönstret.
1. Ange serverns URL och klicka sedan på **OK**.
1. Om felmeddelandet "Kunde inte hitta några registreringar av applet" visas följer du dessa steg för att lösa problemet:

    1. Gå till **Systemadministration \> Inställningar \> Office-programparametrar** i Commerce.
    1. Välj **Initiera programparametrar** på snabbfliken **Programparametrar**.
    1. Klicka på **OK** i bekräftelsemeddelandet.
    1. Välj **Initiera registrering av applet** på snabbfliken **Registrerade appletar**.
    1. Upprepa de tre föregående stegen efter behov.

1. Välj **Design** och sedan **Lägg till tabell**.
1. Välj de enheter som måste läggas till i Excel-arbetsboken för redigering, baserat på de data som ska ändras. Använd följande tabell som referens.

    | Transaktionstyp | Datatabeller som ska användas |
    |------------------|----------------------|
    | Hämtköpstransaktioner, Onlineorder, Asynkrona kundorder, Asynkrona kundofferter | Transaktion (granskningsbar), Försäljningstransaktion (granskningsbar), Betalningstransaktioner (granskningsbara), Momstransaktioner (granskningsbara), Rabattransaktion (granskningsbar), Avgiftstransaktion (granskningsbar) |
    | Bankinsättning | Transaktion (granskningsbar), Bokförda betalningsmedeltransaktioner (granskningsbara) |
    | Lämna pengar i kassaskåp | Transaktion (granskningsbar), Betalningsmedelstransaktioner (kassaskåp) (granskningsbara) |
    | Kassaavstämning | Transaktion (granskningsbar), Kassaavstämningstransaktioner (granskningsbara) |
    | Intäkt, Utgift | Transaktion (granskningsbar), Intäkts‑utgiftstransaktionen (granskningsbara), Betalningstransaktioner (granskningsbara) |
    | Deklarera startbelopp, Borttagning av betalningsmedel, Växelpost, Betalningsmedel för växel, Fakturabetalning, Kundinsättning | Transaktion (granskningsbar), Betalningstransaktioner (granskningsbara) |

    > [!NOTE]
    > Det är viktigt att du bara lägger till en datatabell i varje Excel-arbetsbok. Dessutom måste alla fält som markerats med en nyckelsymbol läggas till i relevant arbetsbok.

1. När arbetsboken har konfigurerats ska du tillämpa de filter som behövs. Se till att samma filter används på alla kalkylblad i filen. Undvik att läsa in för stora datamängder i Excel-filen. I annat fall kan prestandan påverkas vilket medför att Excel och systemet kan gå långsamt. Vi rekommenderar att du alltid använder "Företag" och antingen "Utdragsnummer" eller "Transaktionsnummer" som filter för filen.
1. När filtren har konfigurerats väljer du **Uppdatera** för att läsa in data.
1. Redigera de data som behövs och publicera dem sedan. Om knappen **Publicera** inte är tillgänglig har vissa nyckelfält antagligen inte lagts till i Excel-arbetsboken.

## <a name="additional-resources"></a>Ytterligare resurser

[Redigera och granska hämtköpstransaktioner och transaktioner för kassahantering](edit-cash-trans.md)

[Redigera och granska onlineorder- och asynkrona kundordertransaktioner](edit-order-trans.md)

[Redigera ekonomiska dimensioner för butikstransaktioner](edit-financial-dim.md)

[Lägga till fält i en Excel-arbetsbok för att redigera butikstransaktioner](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]