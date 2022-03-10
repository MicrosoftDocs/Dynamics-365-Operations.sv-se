---
title: Lagerställets platsstatus
description: Det här ämnet ger en översikt över statusfunktionen för lagerställe.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 1b5e1eb651d882e7fbf38f2f2cf8804c28f2154fcb299dbc5caabbecdfab560b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733286"
---
# <a name="warehouse-location-status"></a>Lagerställets platsstatus

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management innehåller flera platsfält som ger dig flexibilitet när du arbetar med och underhålla platser. Du kan ta med platsstatus i frågan platsdirektiv för att få bättre kontroll över lagerflödet.

Följande fyra fält på sidan **platser** spårar information om aktuell status för en plats. De här fälten gör det möjligt för lagerställechefer att få en översikt över statusen för lagerställesplatser. De möjliggör även avancerad rapportering och filtrering.

- **Artikelnummer** – Den artikel som för närvarande finns på platsen. Om lagerstället innehåller flera artiklar är det här fältet tomt.
- **Datum och tid för senaste aktivitet** – Tidsstämpeln för den senaste lagertransaktion som har utförts mot platsen.
- **Åldersdatum** – Det datum då lagret på platsen förts in i lagerstället. Det här värdet beräknas utifrån ID-numrets åldersdatum. Det är korrekt för platser som är en ID-nummerspårade, men är kanske inte korrekt för platser som inte är ID-nummerspårade.
- **Platsstatus** – platsens status. Det finns fyra möjliga värden:

    - **Obestämd** – Platsprofilen kan inte spåra status. Därför är aktuell status okänd.
    - **Tom** – Det finns för närvarande inga lager på platsen.
    - **Plockning** – Utgående transaktioner har utförts mot platsen sedan den senast var tom.
    - **Lagring** – Endast ingående transaktioner har utförts mot platsen sedan den senast var tom.

## <a name="turn-on-the-warehouse-location-status-feature"></a>Aktivera funktionen platsstatus för lagerställe

Innan du kan använda funktionen *platsstatus för lagerställe* den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionens namn:** *platsstatus för lagerställe*

## <a name="set-up-warehouse-location-status"></a>Ställ in platsstatus för lagerställe

### <a name="prepare-the-sample-data-that-is-required-for-the-example-scenario"></a>Förbered de exempeldata som krävs för exempelscenariot

Innan du börjar arbeta i scenariot måste du aktivera exempeldata och ställa in funktionen enligt beskrivningen i det här avsnittet. För att slutföra exempelscenariot måste du använda antingen mobilappen för distributionslagerhantering eller en webbläsarbaserad emulator. I de steg som beskrivs här används mobilappen för distributionslagerhantering. Stegen för den webbläsarbaserade emulatorn är likartade.

#### <a name="use-the-usmf-legal-entity"></a>Använd USMF juridiska personen

Om du vill arbeta genom detta exempelscenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

#### <a name="set-up-location-profiles"></a>Konfigurera platsprofiler

Exempelscenariot kräver att du förbereder två platsprofiler.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.
1. Välj **Redigera** om du vill placera sidan i redigeringsläge.
1. Markera **BULK-06**-profilen.
1. Ange följande värden på snabbfliken **Allmänt**:

    - **Aktivera artikel på plats:** Ange det här alternativet till _Ja_.
    - **Aktivera platsaktivitetens datum och tid:** Ange det här alternativet till _Ja_.
    - **Aktivera platsstatus:** Ange det här alternativet till _Ja_.

    Dessa alternativ bestämmer om referensfälten på platsen är aktiva.

1. Upprepa steg 3 till och med 4 för **PICK-06**-profilen.

> [!NOTE]
> När parametrarna i platsprofilen (**Aktivera artikel i lagerställe**, **Aktivera platsaktivitet**, **Aktivera platsstatus**) ställs in på *Ja*, uppdateras de relevanta platserna omedelbart genom att jobbet före *Konsekvenskontroll för lagerplatsstatus*.

### <a name="scenario"></a>Scenario

1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Välj **Ny**.
1. I dialogrutan **Skapa inköpsorder** på snabbfliken **Leverantör** på fältet **Leverantörskonto**, välj *104*.
1. På snabbfliken **Allmänt** i fältet **Lagerställe**, välj *61*.
1. Välj **OK**.
1. Den nya inköpsordern (IO) öppnas. Den innehåller en tom rad i rutnätet **Inköpsorderrader**. Ställ in följande värden på denna rad:

    - **Artikelnummer:** _A0002_
    - **Kvantitet:** _5_

1. I åtgärdsfönstret på fliken **Inköp** i gruppen **Åtgärder** välj **Bekräfta** för att bekräfta inköpsorder.
1. På den mobila enheten, gå till **Inkommande \> inleverans av inköp**.
1. Markera fältet **PONUM**, ange inköpsordernummer och bekräfta.
1. Markera fältet **ARTIKEL** ange *A0002* som artikelnummer och bekräfta.
1. På sidan **KVT** ange *5* som kvantitet och bekräfta.

    Du kan ange kvantitet på något av följande sätt:

    - Markera plustecknet (**+**) eller minustecknet (**–**) om du vill addera eller subtrahera ett numeriskt värde.
    - Markera det tomma fältet mellan plustecknet (**+**) och minustecknet (**–**) för att öppna det knappsatsen.

1. Bekräfta ditt val av artikelnummer *A0002* och kvantiteten *5*. Ett meddelande om att "arbetet är slutfört" visas längst ned på sidan.
1. Välj menyknappen (kallas ibland för hamburger eller hamburgerknappen) i det övre högra hörnet och välj sedan **Avbryt** för att avsluta **Inleverans av inköp** och gå tillbaka till menyn **Inkommande**.
1. På sidan inköpsorder, välj **Information om arbete** ovanför rutnätet **Inköpsorderrader**.
1. På fliken **Allmänt** observera att värdena **Arbets-ID** och **Målregistreringsskylt** skapades.
1. I avsnittet **Rader** observera värdena **Plats** för arbetstyperna *Plocka* och *Placera*.
1. På den mobila enheten, gå till **Inkommande \> inköpsartikelinförsel**.
1. Markera fältet **ID**, ange arbets-ID och bekräfta.
1. Bekräfta en gång till för att slutföra registreringen *Plocka*.
1. Välj menyknappen i det övre högra hörnet och välj sedan **Klar** för att slutföra arbetet *Plocka*.
1. Anteckna inlagringsplats och bekräfta. Ett meddelande om att "arbetet är slutfört" visas längst ned på sidan.
1. Välj menyknappen i det övre högra hörnet och välj sedan **Avbryt** för att avsluta **inköpsartikelinförsel** och gå tillbaka till menyn **inkommande**.
1. Välj **tillbaka** om du vill återgå till huvudmenyn.
1. I Dynamics 365 Supply Chain Management, gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**.
1. Filtrera på **Plats** och ange inlagringsplats från inköpsorderarbetet. Du bör se följande resultat:

    - Kolumnen **Platsstatus** visar ett värde av *Lagring*, eftersom den sista transaktionen mot den här platsen var en placering.
    - I kolumnen **artikelnummer** visas värdet *A0002* eftersom artikeln har inlevererats och placerats i lagerstället.
    - I kolumnen **Datum och tid för senaste aktivitet** visar tidsstämpeln för datum och tid då arbetet avslutades på platsen.

1. I mobilenheten gå till **Kvalitet \> Rörelse**.
1. Markera fältet **LOC/LP** ange den plats du antecknade i föregående steg.
1. Bekräfta informationen som visas. Anteckna vilket ID-nummer som har skapats.
1. På skärmen **Till information** välj fältet **LOC/LP** och ange *06A07R2S1B* som plats att flytta objektet till.
1. På skärmen **Till information** bekräftar du värdet **LP** (målregistreringsskylt), som genereras automatiskt. Ett meddelande om att "arbetet är slutfört" visas längst ned på sidan.
1. Välj menyknappen i det övre högra hörnet och välj sedan **Avbryt** för att avsluta **Rörelse** och gå tillbaka till menyn **Kvalitetshantering**.
1. Välj **tillbaka** om du vill återgå till huvudmenyn.
1. I Dynamics 365 Supply Chain Management, gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**.
1. Uppdatera sidan **Platser** och visa den ursprungliga inlagringsplatsen igen. Observera att fältet **Platsstatus** nu är *tomt* och att kolumnen **Artikelnummer** är tom.
1. Visa posten för plats *06A07R2S1B* och observera att värdet **status** har ändrats till *lagring* och fälten **artikelnummer** och **senaste aktivitetsdatum och tid** har uppdaterats.
1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Välj **Ny**.
1. I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj *US-002*.
1. I fältet **Lagerställe**, välj *61*.
1. Välj **OK**.
1. Den nya försäljningsordern öppnas. Den innehåller en tom rad i rutnätet **Försäljningsorderrader**. Ställ in följande värden på denna rad:

    - **Artikelnummer:** _A0002_
    - **Kvantitet:** _1_

1. På snabbfliken **Försäljningsorderrader** i menyn **Lager** välj **Reservation**.
1. I sidan **Reservation**, välj **Reservera parti** för att reservera orderrad. Välj sedan knappen **Stäng** (**X**) överst till höger. för att stänga sidan.
1. I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.
1. På snabbfliken **Försäljningsorderrader** på menyn **Lagerställe**, välj **Arbetsdetaljer**.
1. Kopiera värdet för **arbets-ID** som skapades.
1. På den mobila enheten, gå till **Utgående \> Försäljningsplockning**.
1. Markera fältet **ID**, ange arbets-ID du kopierade tidigare och bekräfta.
1. På sidan **Försäljningsorder: plockning** föreslår fältet **LOC** plockningsplatsen som den inlagringsplats skapades tidigare. Gör en notering av plats.
1. Markera fältet **LOC**, ange plats och bekräfta.
1. Välj fältet **LP**, ange det ID-nummer som du gjorde en notering för under rörelseaktiviteten och bekräfta.
1. Markera fältet **Artikel** ange *A0002* som artikelnummer och bekräfta.
1. På sidan **KVT** ange *1* som kvantitet och bekräfta.

    Du kan ange kvantitet på något av följande sätt:

    - Markera plustecknet (**+**) eller minustecknet (**–**) om du vill addera eller subtrahera ett numeriskt värde.
    - Markera det tomma fältet mellan plustecknet (**+**) och minustecknet (**–**) för att öppna det knappsatsen.

1. Markera fältet **MÅL LP** ange ett användardefinierat målnummer-ID och bekräfta det.
1. Bekräfta en gång till för att slutföra plockningsarbetet. Ett meddelande om att "arbetet är slutfört" visas längst ned på sidan.
1. Välj menyknappen i det övre högra hörnet och välj sedan **Avbryt** för att slutföra plockningsarbetet och gå tillbaka till menyn **Utgående**.
1. I Dynamics 365 Supply Chain Management, gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**.
1. Filtrera på **Plats** och ange plockningsplats från försäljningsorderarbetet.
1. Observera att fältet **Platsstatus** för den plats som försäljningsorderarbetet plockas från nu är inställt på *Plocka* och fältet **Datum och tid för senaste aktivitet** har uppdaterats.

> [!NOTE]
> Platsfälten uppdateras endast av lagerställetransaktioner. Om du flyttar lagret med hjälp av en journal eller andra icke-WHS-processer, uppdateras inte fälten.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]