---
title: "Arbetsyta för räkenskapsperiodens stängning"
description: "Det här avsnittet innehåller en översikt över arbetsytan Räkenskapsperiodens stängning och den associerade konfigurationen."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: ba0d709d123f56edb2a5287376c06c1f41181b1c
ms.lasthandoff: 03/31/2017


---

# <a name="financial-period-close-workspace"></a>Arbetsyta för räkenskapsperiodens stängning

Det här avsnittet innehåller en översikt över arbetsytan Räkenskapsperiodens stängning och den associerade konfigurationen.

Arbetsyta för räkenskapsperiodens stängning

Den **räkenskapsperioden stängs** arbetsytan kan du spåra dina ekonomiska utgående processer mellan företag, områden och personer. Beroende på din vy av den **räkenskapsperioden stängs** arbetsytan visas antingen till alla uppgifter och status för ett utgående schema eller enbart de aktiviteter som har tilldelats dig. 

Du måste först markera ett avslutande schema överst på arbetsytan. Alla data som visas på arbetsytan filtreras sedan genom ett markerad stängning schemat.

### <a name="summary-tiles"></a>Sammanfattningsrutor

Rutorna **Sammanfattning** ger en översikt över processen och indikatorer hjälper dig att följa upp stängningsprocessen. Du kan se aktiviteter som passerat förfallodatum återstående aktiviteter för idag och uppgifter som förfaller idag, men är spärrad p.g.a. beroenden alla återstående aktiviteter för processen. Denna information används för alla företag som ingår i ett markerad stängning schemat.

### <a name="tasks-and-status-section"></a>Avsnittet Uppgifter och status

I den **uppgifter och status** avsnittet status för hela schemat stängningen är uppdelad på flera olika sätt: status genom att företag och status efter status per person som är ansvarig. Du kan visa statusen för alla aktiviteter i stängningen schemalägga endast uppgifter som förfaller idag eller uppgifter som har förfallit genom att ändra filtret överst i listan på kortet. Du kan också välja företagsfilter att visa status för ett specifikt företag. Varje flik status ger en uppdelning av både i procent som har slutförts och hur många uppgifter som återstår. Klicka på kortet eller **Visa detaljer** åtgärd att filtrera detaljerad aktivitetslistan efter det markerade kortet. 

Den sista fliken är för detaljerad uppgiftslistan. Listan visar hela uppgiftslistan och filtreras så att bara de aktiviteter som du är intresserad av visas. Du kan filtrera listan på flera sätt. Du kan filtrera efter förfallodatum, närstående bolag och tillhörande området uppgift. Du kan också välja att visa eller dölja slutförda aktiviteter i aktivitetslistan. 

Två indikatorer används för uppgifter:

-   Ett utropstecken, ikon anger att aktiviteten är försenad. För aktiviteter som är förfallna markeras förfallodatum med rött.
-   En hänglåsikon indikerar att uppgiften är beroende av andra uppgifter som ännu inte slutförts. En uppgift som har blockerats av beroenden kan inte markeras som slutförd. Du kan ange beroenden för en aktivitet med hjälp av den **ange beroende** åtgärd.

Aktivitetens namn är en hyperlänk till sidan åtgärder eller andra webbsidan Microsoft Dynamics 365 där användaren måste gå för att slutföra arbetet. Anger den aktuella hyperlänken genom att använda de **aktivitetslänk** när du redigerar eller skapar en uppgift. 

Du kan koppla filer, anteckningar, bilder och URL-adresser till en aktivitet med hjälp av den **bifogade** åtgärd. Exempelvis anger journalnummer som används som en del av en aktivitet, lägga till kommentarer om en viss aktivitet eller koppla en rapportfil som skrevs ut för en aktivitet. En ikon i den **bilaga** för aktiviteten om det finns en bifogad fil. 

Den **Slutför uppgiften** alternativ manuellt väljas när aktiviteten är avslutad. När en aktivitet har markerats som slutförd, den **slutförts datum** uppdateras automatiskt fältet till aktuellt datum och aktuell tid. Indikatorer beroendet uppdateras också enligt önskemål.

## <a name="all-financial-period-close-tasks-list-page"></a>Listsida Alla uppgifter för räkenskapsperiodens stängning
Du kan visa alla aktuella och föregående perioder Stäng uppgifter från den **stänga räkenskapsperioden för alla aktiviteter** listsida. Den här listsidan passar bäst för historisk analys av stängningen, eftersom den innehåller information om de planerade förfallodatum, det verkliga slutdatumet och den person som har slutfört uppgiften. Du kan enkelt exportera informationen på den här sidan till Microsoft Excel för rapportering och granska syften.

## <a name="financial-period-close-configuration-page"></a>Sidan Räkenskapsperiodens stängningskonfiguration
Innan du kan använda den **räkenskapsperioden stängs** arbetsytan måste du konfigurera hur Microsoft Dynamics 365 för åtgärder med hjälp av den **ekonomiska period nära konfigurationen** sida. (Klicka på **redovisning**&gt;**periodstängning**&gt;**ekonomiska period nära konfigurationen**.)

### <a name="resources"></a>Resurser

I den **resurser** och definiera de personer som är inblandade i utgående processer. Vilken medarbetare som ansvarar för en aktivitet stängningen måste först tilldelas här. Du måste också ange medarbetarvyn i arbetsytan. Följande alternativ är tillgängliga:

-   **Endast tilldelade uppgifter** – Användaren ser enbart de uppgifter som är tilldelade honom eller henne.
-   **All uppgifter och statusar** – Användaren ser alla bokslutsuppgifter och statusar för hela processen.

Användare som har behörighet att visa endast sina tilldelade uppgifter, kommer inte att vara i stånd att lägga till uppgifter i uppgiftslistan, redigera uppgifter eller ta bort uppgifter från uppgiftslistan.

### <a name="task-areas"></a>Uppgiftsområden

Du använder uppgiftområden för att gruppera bokslutsuppgifter i logiska området baserat på ägarskap i din organisation. Exempelvis kan Leverantörsreskontra, Kundreskontra eller Huvudbok användas som uppgiftområden.

### <a name="calendars"></a>Kalendrar

Skapa och redigera ekonomiska stängning kalendrar på fliken kalendrar.  Detta är där du kan definiera arbetsdagar för stängningsprocesserna och används för att schemalägga aktiviteter för stängning.  Skapa en ny kalender och ange arbetsdagar som ska användas för att schemalägga aktiviteten.  Det är bäst att skapa en kalender för en lång tidsperiod, till exempel ett år, eller flera år eftersom den kan redigeras när de har skapats.  När du har skapat kalendern, klicka på Redigera för att uppdatera kalendern för särskilda dagar, t ex helgdagar.  Stänga aktiviteter schemaläggs när kontrollen har värdet på Öppna dagar.  Om du stänga aktiviteter inte ska schemalägga på en viss dag, ha dagen kontrollvärdet stängd.

### <a name="templates"></a>Mallar

Du använder en ekonomiska Stäng mall för att definiera aktiviteterna som ingår i en stängningsprocessen. Uppgift för stängning är återkommande arbetsinsatsen tilldelas en person att slutföra som en del av varje stängningsprocessen. I mallen ett relativt förfallodatum datumet måste anges för varje uppgift för stängning. Relativt förfallodatum infaller antal dagar före eller efter definierade periodslut datumet som aktiviteten måste göras varje period. Förfallodatum tid har tilldelats varje aktivitet. Förfallotiden anges med hänsyn till din tidszon och konverteras till den lokala tidszonen för varje användare. 

Du kan tilldela en uppgift i mallen till ett eller flera företag, om detta tillämpas. Om en annan person har tilldelats slutföra den arbetsinsatsen i varje företag, kan det vara en god idé att skapa flera åtgärder för samma arbetsinsats. Skapa en uppgift för varje företag. 

Den **aktivitetslänk** är associerad med uppgiften arbetsinsatsen och kan användas för att gå direkt till motsvarande sida från aktivitetslänken på arbetsytan. Till exempel en avslutande aktivitet valuta omvärdering processen för leverantörsreskontra kopplad till tillhörande **omvärdering i utländsk valuta** sida i Microsoft Dynamics 365 för operationer. Du kan även länka till en extern URL-adress. 

> [! Tips] om du vill länka en viss rapport Management Reporter till en finansiell period nära aktivitet du kan använda rapporten URL. Öppna rapporten i rapportdesign till URL: en för rapporten och klicka sedan på **filen**&gt;**Visa rapport** så att rapporten öppnas i en webbläsare. Du kan sedan kopiera URL:n i webbläsarens adressfält och klistra in den i **uppgiftlänkens** **URL**-fält. 

Du kan definiera samband i mallen. Om en aktivitet har ställts in att vara beroende av en eller flera aktiviteter, kan aktiviteten inte markeras som slutförd förrän alla beroenden har slutförts. 

Du kan skapa flera ekonomiska Stäng mallar. Du kan sedan använda de olika mallarna spåra avslutande processerna för olika periodtyper t ex slutet av månaden eller årets slut eller företag som använder olika utgående processer kan spåras. När en mall har skapats kan du kopiera den till en ny mall och gör nödvändiga ändringar. Du kan tilldela varje stängning schema endast en mall.

### <a name="closing-schedules"></a>Stängningstidsplaner

Du kan använda ett avslutande schema tilldelas en nära ekonomiska mall till en viss tidsperiod som ska stängas. Uppgifterna från mallen skapas sedan automatiskt för den angivna perioden och det nya UB-schemat läggs till i arbetsytan. När du skapar ett nytt schema stängning, den **slutdatum** används för att fastställa det faktiska förfallodatumet datum för stängning aktiviteter, baserat på relativa förfallodatum som används i ekonomiska Stäng mallen. 

Tilldela en kalender för UB-schemat vill ange arbetsdagar för schemaläggningen. Om du inte definierar en specifik kalender uppgiften förfaller datum kommer att användas för alla dagar i veckan. 

Du måste också ange företag som ska associeras med det sista schemat. Om mallen uppgifter har tilldelats till flera företag, skapas separata uppgifter för varje företag som avslutande resurstillgänglighet och tilldelas uppgiften mall. 

När ett schema stängningen är slutförd väljer du den **stängd** alternativ för den. Tidigare aktiviteter kommer att vara tillgänglig från den **stänga räkenskapsperioden för alla aktiviteter** listsida, men stängning schemat tas bort från arbetsytan. När ett utgående schema har markerats som **stängd**, du kommer inte att kunna lägga till aktiviteter, redigera aktiviteter eller ta bort uppgifter.


