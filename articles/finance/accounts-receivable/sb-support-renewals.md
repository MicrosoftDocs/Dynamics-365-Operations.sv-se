---
title: Support och förnyelser
description: Detta ämne beskriver hur du konfigurerar och använder support- och förnyelseprocessen för försäljningsorder för att skapa ett faktureringsschema för förnyelseartikelar.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: d59eee6e858c4f0051ec103adc4e1e99e79feec9
ms.sourcegitcommit: 4d7bc52e6cdf6afce3793893ba2aa07176302314
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560497"
---
# <a name="support-and-renewals"></a>Support och förnyelser 

I det här avsnittet beskrivs hur du registrerar supportartiklar eller förnyelseartiklar när du registrerar försäljningsorder. Dessa artiklar används för att beräkna debiteringsbeloppet för det ursprungliga supportkontraktet och/eller det förnyelsebelopp som används när en faktureringstidsplan skapas vid prenumerationsfakturering. Ditt företag säljer till exempel en server till en kund, och du erbjuder ett abonnemang för datasäkerhetskopiering för det första året tillsammans med ett alternativ för att förnya det abonnemanget varje år. *Supportartikeln* är abonnemanget för det första året, och *förnyelseartikeln* är förnyelsen för respektive på följande år.

Du kan ange information för supportkontraktet, förnyelsekontraktet eller båda. När du registrerar supportkontraktsinformationen läggs endast supportartikeln till i försäljningsordern. När du anger informationen rörande förnyelsekontraktet används förnyelseartikeln för att skapa en faktureringstidsplan.

## <a name="support-and-renewal-setup"></a>Konfiguration av support och förnyelse

På sidan **Support- och förnyelsesupport** kan du konfigurerar olika supportnivåer för support- och förnyelseartiklar. Supporten eller förnyelsen kan vara en procentandel av det ursprungliga artikelbeloppet, eller också kan det vara ett standardbelopp.

Du kan välja standardnivåer för support på sidan **Parametrar för återkommande kontraktfakturering**.

Ett företag kan till exempel erbjuda följande support- och förnyelsenivåer.

| Supportnivå | Supportprocent | Förnyelseprocent |
|---|---|---|
| Obegränsat | 40 % | 30 % |
| Guld | 25 % | 18 % |
| Silver | 20 % | 14 % |
| Brons | 15 % | 10 % |

Följ de här stegen om du vill skapa en nivå för support eller förnyelse.

1. På sidan **Support- och förnbyelsenivåer** väljer du **Ny**.
2. Ange ett unikt namn i fältet **Supportnivå**.
3. Ange en beskrivning i fältet **beskrivning**.
4. Välj beräkningsmetod för support i fältet **Beräkningsmetod för support**. Om du väljer **Procent** anger du en supportprocent i fältet **Supportprocent**.
5. Välj förnyelseberäkningsmetoden i fältet **Beräkningsmetod för förnyelse**. Om du väljer **Procent** anger du en förnyelseprocent i fältet **Förnyelseprocent**.
6. Välj **Spara**.

### <a name="fields"></a>Fält

Sidan **Support- och förnyelsenivåer** innehåller följande fält.

| Fält | Beskrivning |
|---|---|
| Supportnivå | En unik identifierare för support- eller förnyelsenivå (till exempel **Guld** eller **Silver**). |
| Beskrivning | En beskrivning av nivån för support eller förnyelse. |
| Beräkningsmetod för support | Välj beräkningsmetod för support för nivån: **Procent** eller **Standardbelopp**. |
| Supportprocent | Om du har valt **Procent** som beräkningsmetod för support anger du vilken procentsats som ska användas för att beräkna priset för supportartikeln. Om du valde **Standardbelopp** som beräkningsmetod anges beloppet när transaktionen skapas. |
| Beräkningsmetod för förnyelse | Välj beräkningsmetod för förnyelse för nivån: **Procent** eller **Standardbelopp**. |
| Förnyelseprocent | Om du har valt **Procent** som förnyelseberäkningsmetod anger du vilken procentsats som ska användas för att beräkna priset för förnyelseartikeln. Om du valde **Standardbelopp** som beräkningsmetod anges beloppet när transaktionen skapas. |

## <a name="support-and-renewal-process"></a>Support- och förnyelseprocess

Funktionerna för support och förnyelse kan tillämpa olika supportnivåer på artiklar och uppdatera förnyelseinformation i Abonnemangsfakturering.

Innan du använder funktionen för stöd och förnyelse måste följande uppgifter slutföras.

1. På sidan **Support- och förnyelsernivåer** skapar du minst en nivå för support och förnyelse.
2. På sidan **Artikelkonfiguration** associerar du en artikel med support- och förnyelseartiklar. Den här uppgiften är endast obligatorisk om du vill ställa in standardvärden för support- och/eller förnyelseartiklar.
3. På sidan **Faktureringsparametrar för återkommande kontrakt** anger du standardinställningar för support och nya faktureringsscheman.

Följ de här stegen om du vill använda olika supportnivåer för artiklar och uppdatera förnyelseinformation.

1. På sidan **Alla försäljningsorder** skapar du en försäljningsorder.
2. På snabbfliken **Försäljningsorderrader** lägger du till en artikel.
3. På fliken **Faktura** väljer du **Support och förnyelse \> Lägg till support och förnyelse**.
4. På sidan **Support- och förnyelseprocess** uppdateras huvudavsnittet med inställningarna från sidan **Faktureringsparametrar för återkommande kontrakt**. Dessa värden gäller för alla support- och förnyelseartiklar. (Om faktureringsfrekvensen till exempel är inställd på **Årligen** har alla försäljningsrader som har skapats med en förnyelseartikel en årlig frekvens.) Om du vill koppla försäljningsordern till en befintlig faktureringstidsplan väljer du ett värde i fältet **Tidsplansnummer för fakturering**.
5. Om du vill ändra startdatumet för support eller för förnyelse ställer du in alternativet **Åsidosätt startdatum** som **Ja**.
6. Om du vill lägga till eller redigera supportartikeln markerar du kryssrutan **Support** innan du anger en supportartikel i fältet **Supportartikel**. Artikeln läggs till i försäljningsordern.
7. Om du vill lägga till förnyelseartikeln markerar du kryssrutan **Förnyelse** innan du anger en förnyelseartikel i fältet **Förnyelseartikel**. När försäljningsordern faktureras skapas ett faktureringsschema som innehåller artikeln.
8. Välj **OK**.
9. På fliken **Generera** väljer du **Faktura**. När försäljningsordern bokförs skapas faktureringsschemat. Ett meddelande som innehåller informationen om faktureringsschema visas i meddelandeinformationen.
10. På listsidan **Alla/aktiva faktureringstidsplaner** väljer du faktureringstidsplanens nummer om du vill granska faktureringstidsplanens detaljer på sidan **Faktureringstidsplaner**.
11. På snabbfliken **Rader i faktureringstidsplan** väljer du **Support och förnyelse** för att granska detaljer för de rader som har skapats.

> [!NOTE]
> Om förnyelsestartdatumet för en tidsplansrad för fakturering måste ändras kan du redigera värdet **Startdatum** för raden på sidan **Faktureringstidsplaner**. När du öppnar sidan **Visa faktureringsdetaljer** för raden uppdateras fältet **Startdatum för fakturering** med det nya datumet. Värdet för **Faktureringsslutdatum** räknas om baserat på faktureringsfrekvensen. Startdatumet för förnyelse kan bara uppdateras om den första fakturan för det fakturerade faktureringsschemat inte har skapats och bokförts. När den första fakturan har skapats och bokförts går det inte att redigera startdatumet.

Support- och kundtjänstprocessen är bara tillgänglig för försäljningsordern. När du lägger till support- och förnyelseartiklar i en försäljningsorder kan du skapa ett nytt faktureringsschema eller lägga till förnyelseartikeln i ett befintligt faktureringsschema.

## <a name="support-and-renewal-audit"></a>Granskning av support och förnyelse

På sidan **Support och granskning av förnyelse** kan du granska information om de fakturatidsplansrader som har skapats från förnbyelseartikeln i en försäljningsorder. Detta alternativ är endast tillgängligt när radartikeln i faktureringstidsplanens rad är en förnyelseartikel.

Om du vill redigera support- och förnyelseinformation för en faktureringstidsplansrad följer du dessa steg.

1. På sidan **Alla faktureringstidsplaner** väljer du faktureringstidsplanens nummer.
2. I avsnittet **Faktureringstidsplansrader** väljer du en rad och sedan **Support och förnyelse**.
3. Granska all information om support- eller förnyelseartikeln.
4. Ändra supportnivån, förnyelseprocentsatsen eller beloppet efter behov, och ange sedan ett värde i fältet **Orsak till ändring**.
5. Välj **Process**.

### <a name="fields"></a>Fält

Sidan **Support- och förnyelsegranskning** innehåller följande fält.

| Fält | Beskrivning |
|-------|-------------|
| Artikelnummer | Artikelnummer för rad för faktureringsplan. |
| Produktnamn | Produktnamnet. |
| Nivå på supportplan | Visa eller ändra supportnivån för förnyelseartikeln. |
| Förnyelseprocent | Ange den förnyelseprocentsats som används när enhetspriset beräknas för en förnyelseartikel i en faktureringstidsplan. |
| Förnyelsebelopp | Ange det förnyelsebelopp som används när enhetspriset beräknas för en förnyelseartikel i en faktureringstidsplan. |
| Orsak till ändringen | Ange orsaken till att du ändrar support- och ändringsinformationen. Du måste ange en orsak när du ändrar värdet för **Förnyelseprocent**, **Förnyelsebelopp** eller **Nivå för supportplan**. |
| Ursprunglig försäljningsartikel | Det ursprungliga numret för försäljningsartikel i försäljningsordern. |
| Ursprungligt nettobelopp | Det ursprungliga nettobeloppet för artikeln. |
| Ursprunglig supportnivå | Den ursprungliga supportnivån för artikeln. |
| Ursprunglig förnyelseprocent | Den ursprungliga förnyelseprocenten för artikeln. |
| Ursprungligt förnyelsebelopp | Det ursprungliga förnyelsebeloppet för artikeln. |
| **Rutnät** | |
| Ursprunglig supportnivå | Tidigare supportnivå. |
| Ursprunglig förnyelseprocent | Tidigare förnyelseprocent. |
| Ursprungligt förnyelsebelopp | Tidigare förnyelsebelopp. |
| Ändrades av | Användarnamn för den användare som utförde ändringen. |
| Datum och tid för ändring | Det datum då förändringen inträffade. |
| Orsak | Orsaken till ändringen. |
