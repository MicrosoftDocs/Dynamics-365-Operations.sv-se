---
title: "Arbetsyta för räkenskapsperiodens stängning"
description: "Det här avsnittet innehåller en översikt över arbetsytan Räkenskapsperiodens stängning och den associerade konfigurationen."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 788b0af30eb750cad8f958ecc4c33cf989b2a417
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="financial-period-close-workspace"></a>Arbetsyta för räkenskapsperiodens stängning

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller en översikt över arbetsytan Räkenskapsperiodens stängning och den associerade konfigurationen.

Arbetsyta för räkenskapsperiodens stängning

Arbetsytan **Räkenskapsperiodslut** låter dig spåra dina ekonomiska processer som håller på att stängas, sett över företag, områden och personer. Beroende på din vy över arbetsytan **Räkenskapsperiodslut** visas antingen alla uppgifter och status för ett utgående schema eller enbart de aktiviteter som har tilldelats dig. 

Du måste först markera ett avslutande schema överst på arbetsytan. Alla data som visas på arbetsytan filtreras sedan genom det markerade stängningsschemat.

### <a name="summary-tiles"></a>Sammanfattningsrutor

Rutorna **Sammanfattning** ger en översikt över processen och indikatorer hjälper dig att följa upp stängningsprocessen. Du kan se aktiviteter som passerat förfallodatum, återstående aktiviteter för idag, uppgifter som förfaller idag men som är spärrade p.g.a. beroenden, samt alla återstående aktiviteter för processen. Denna information används för alla företag som ingår i det markerade, utgående schemat.

### <a name="tasks-and-status-section"></a>Avsnittet Uppgifter och status

I avsnittet **Uppgifter och status** delas statusen för hela det utgående schemat upp på flera olika sätt: status efter företag, status efter område samt status per ansvarig person. Du kan visa statusen för alla aktiviteter i det utgående schemat, endast uppgifter som förfaller idag eller uppgifter som har förfallit genom att ändra filtret överst i listan på kortet. Du kan också välja företagsfilter för att visa status för ett specifikt företag. Varje statusflik tillhandahåller en uppdelning efter såväl slutförd procent och hur många uppgifter som återstår. Klicka på kortet eller åtgärden **Visa detaljer** för att filtrera den detaljerade aktivitetslistan efter det markerade kortet. 

Den sista fliken är för den detaljerade uppgiftslistan. Listan visar hela uppgiftslistan och kan filtreras så att bara de aktiviteter som du är intresserad av visas. Du kan filtrera uppgiftslistan på flera sätt. Du kan exempelvis filtrera efter förfallodatum, tillhörande företag och tillhörande område. Du kan också välja att visa eller dölja slutförda aktiviteter i aktivitetslistan. 

Två indikatorer används för uppgifter:

-   Ikonen utropstecken anger att aktiviteten är försenad. För aktiviteter som är förfallna markeras förfallodatum med rött.
-   En hänglåsikon indikerar att uppgiften är beroende av andra uppgifter som ännu inte har slutförts. En uppgift som har blockerats av beroenden kan inte markeras som slutförd. Du kan ange beroenden för en aktivitet med hjälp av åtgärden **Ange beroende**.

Aktivitetens namn är en hyperlänk till Microsoft Dynamics 365 for Operations-sidan eller en annan webbsida dit användaren måste bege sig för att slutföra arbetet. Du kan ställa din denna hyperlänk genom att använda fältet **Uppgiftslänk** när du redigerar eller skapar en uppgift. 

Du kan bifoga filer, anteckningar, bilder och URL-adresser till en aktivitet med hjälp av åtgärden **Bilagor**. Du kan exempelvis ange journalnummer som används som en del av en aktivitet, lägga till kommentarer om en viss aktivitet eller bifoga en rapportfil som skrevs ut för en aktivitet. En ikon syns i kolumnen **Bilaga** för aktiviteten om det finns en bifogad fil. 

Alternativet **Uppgiften slutförd** måste väljas manuellt när aktiviteten är avslutad. När en aktivitet har markerats som slutförd, uppdateras fältet **Datum för slutförande** automatiskt till aktuellt datum och aktuell tid. Beroendeindikatorer uppdateras också om tillämpbart.

## <a name="all-financial-period-close-tasks-list-page"></a>Listsida Alla uppgifter för räkenskapsperiodens stängning
Du kan visa alla aktuella och föregående periodstängningsuppgifter från listsidan **Alla ekonomiska periodstängningsuppgifter**. Den här listsidan passar bäst för historisk analys av stängningen, detta eftersom den innehåller information om planerade förfallodatum, verkligt slutdatum och den person som har slutfört uppgiften. Du kan enkelt exportera informationen på den här listsidan till Microsoft Excel i rapporterings- och granskningssyfte.

## <a name="financial-period-close-configuration-page"></a>Sidan Räkenskapsperiodens stängningskonfiguration
Innan du kan använda arbetsytan **Räkenskapsperiodens stängning** måste du konfigurera processen i Microsoft Dynamics 365 for Operations på sidan **Räkenskapsperiodens stängningskonfiguration**. (Klicka på **Huvudbok** &gt; **Periodstängning** &gt; **Räkenskapsperiodens stängningskonfiguration**.)

### <a name="resources"></a>Resurser

På fliken **resurser** definierar du de personer som är inblandade i utgående processer. Alla medarbetare som ansvarar för en stängningsaktivitet måste först tilldelas här. Du måste också ange medarbetarvyn i arbetsytan. Följande alternativ är tillgängliga:

-   **Endast tilldelade uppgifter** – Användaren ser enbart de uppgifter som är tilldelade honom eller henne.
-   **All uppgifter och statusar** – Användaren ser alla bokslutsuppgifter och statusar för hela processen.

Användare som har behörighet att visa endast sina tilldelade uppgifter, kommer inte att vara i stånd att lägga till uppgifter i uppgiftslistan, redigera uppgifter eller ta bort uppgifter från uppgiftslistan.

### <a name="task-areas"></a>Uppgiftsområden

Du använder uppgiftområden för att gruppera bokslutsuppgifter i logiska området baserat på ägarskap i din organisation. Exempelvis kan Leverantörsreskontra, Kundreskontra eller Huvudbok användas som uppgiftområden.

### <a name="calendars"></a>Kalendrar

Skapa och redigera ekonomiska stängningskalendrar på fliken Kalendrar.  Det är här som du kan definiera arbetsdagar för stängningsprocesser, vilket används för att schemalägga aktiviteter för stängning.  Skapa en ny kalender och ange de arbetsdagar som ska användas för att schemalägga uppgiften.  Det är bäst att skapa en kalender för en lång tidsperiod, till exempel ett år eller flera år, eftersom den kan redigeras när den har skapats.  När du har skapat kalendern, klicka på knappen Redigera för att uppdatera kalendern för särskilda dagar, t.ex. helgdagar.  Stängningsaktiviteter schemaläggs på dagar då kontrollvärdet har angetts som Öppet.  Om stängningsaktiviteter inte ska schemaläggas på en viss dag, bör kontrollvärdet för den dagen vara Stängd.

### <a name="templates"></a>Mallar

Du använder en mall för ekonomisk stängning för att definiera alla aktiviteter som ingår i en stängningsprocess. En stängningsuppgift är en återkommande arbetsinsats som tilldelas en person att slutföras som en del av varje stängningsprocess. I mallen måste du definiera ett relativt förfallodatum för varje stängningsuppgift. Relativt förfallodatum är det antal dagar före eller efter det definierade periodslutsdatumet som aktiviteten förfaller varje period. Förfallodatum tilldelas även varje aktivitet. Förfallotiden anges med hänsyn till din tidszon, och konverteras till den lokala tidszonen för varje användare. 

Du kan tilldela en uppgift i mallen till ett eller flera företag där uppgiften tillämpas. Om en annan person tilldelas att slutföra arbetsinsatsen i respektive företag, kan det vara en god idé att skapa flera åtgärder för samma arbetsinsats. Skapa en uppgift för varje företag. 

Menyobjektet **Uppgiftslänk** är associerat med uppgiftens arbetsinsats, och kan användas för att gå direkt till motsvarande sida från aktivitetslänken på arbetsytan. En avslutningsaktivitet i syfte att köra valutaomvärderingsprocessen för leverantörsreskontra kan exempelvis kopplas i till tillhörande sida för **Omvärdering i utländsk valuta** i Microsoft Dynamics 365 for Operations. Du kan även länka till en extern URL-adress. 

> [Tips] Om du vill länka en viss Management Reporter-rapport till en bokslutsuppgift, kan du använda rapportwebbadressen. För att öppna rapportwebbadressen öppnar du rapporten i rapportdesignern och klickar på **Fil** &gt; **Visa rapport** för att öppna rapporten i en webbläsare. Du kan sedan kopiera URL:n i webbläsarens adressfält och klistra in den i **uppgiftlänkens** **URL**-fält. 

Du kan definiera samband i mallen. Om en uppgift har ställts in så att den är beroende av en eller flera uppgifter, kan uppgiften inte markeras som slutförd förrän alla beroenden har slutförts. 

Du kan skapa flera mall för ekonomisk stängning. Du kan sedan använda de olika mallarna för att spåra avslutande processer för olika periodtyper, t.ex. månads- eller årsslut, eller för att spåra företag som använder olika utgående processer. När en mall har skapats kan du kopiera den till en ny mall och utföra nödvändiga ändringar. Du kan bara tilldela en mall till respektive stängningsschema.

### <a name="closing-schedules"></a>Stängningstidsplaner

Du kan använda ett stängningsschema för att tilldela en mall för ekonomisk stängning till en viss ekonomisk period som ska stängas. Uppgifterna från mallen skapas sedan automatiskt för den angivna perioden, och det nya stängningsschemat läggs till på arbetsytan. När du skapar ett nytt stängningsschema används fältet **Periodslutdatum** för att fastställa det faktiska förfallodatumet för stängningsaktiviteter, baserat på det relativa förfallodatum som används i den ekonomiska stängningsmallen. 

Tilldela en lämplig kalender för stängningsschemat vi syfte att ange vilka arbetsdagar som ska användas för schemaläggningen. Om du inte definierar en specifik kalender kommer uppgiftens förfallodatum att använda alla dagar i veckan. 

Du måste också ange de företag som ska associeras med stängningsschemat. Om malluppgifter tilldelas till flera olika företag, skapas separata uppgifter för varje företag som finns i stängningsschemat och som tilldelats malluppgiften. 

När ett stängningsschema är slutfört väljer du alternativet **Stängd** för den. Tidigare aktiviteter är fortsatt tillgängliga från listsidan **Alla stängningsuppgifter för ekonomisk period**, men stängningsschemat tas bort från arbetsytan. När ett stängningsschema har markerats som **Stängt** kan du inte lägga till aktiviteter i det, redigera aktiviteter eller ta bort uppgifter.




