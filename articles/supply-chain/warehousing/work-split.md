---
title: Arbetsdelning
description: Det här avsnittet innehåller information om funktionen arbetsdelning. Med den här funktionen kan du dela upp stora arbetsorder i flera mindre arbetsorder som du sedan kan tilldela till flera lagerarbetare. På så sätt kan samma arbete plockas samtidigt av flera lagerarbetare.
author: mirzaab
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6844f3962562a02609333ef7d6963801852af4b0
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344156"
---
# <a name="work-split"></a>Arbetsdelning

Med funktion för arbetsdelning kan du dela stora arbets-ID (det vill säga arbetsorder som har flera rader) i flera mindre arbets-ID som du sedan kan tilldela till flera lagerarbetare. På så sätt kan samma nummer för arbetsskapande plockas samtidigt av flera lagerarbetare.

> [!IMPORTANT]
> Du kan bara dela arbetsorder som har statusen *öppen* eller *pågående*.

## <a name="turn-on-the-work-split-functionality"></a>Aktivera funktionen dela arbete

Innan du kan använda funktionen för delning av resurser måste du aktivera funktionen och dess nödvändiga funktion i systemet. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.

Börja med att aktivera funktionen *Arbetsspärr för hela organisationen* om den inte redan är aktiverad. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *Arbetsspärr för hela organisationen*

> [!NOTE]
> När den här funktionen aktiveras används en datauppgradering automatiskt när funktionen har aktiverats för alla juridiska personer.

Aktivera sedan funktionen *Arbetsdelning*, som visas på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionens namn:** *Arbetsdelning*

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a>Förbättringar av arbetsuppgifter och alla arbetssidor

Funktionen *Arbetsdelning* lägger till följande två knappar på **Arbete** i åtgärdsfönstret för sidan **Arbetsuppgifterna** och **Allt arbete**:

- **Dela arbetsuppgift** – Dela aktuellt arbets-ID i flera mindre arbete-ID som kan bearbetas av olika personer.
- **Avbryt arbetsdelningssession** – Avbryt arbetssessionen för arbetet och gör arbetet tillgängligt för bearbetning.

![Knappar för Dela upp arbete- och Avbryt arbetsdelning-sessioner.](media/Work_split_buttons.png "Knappar för dela upp arbete och avbryt arbetsdelningssessioner")

> [!IMPORTANT]
> Knappen **Dela arbete** är inte tillgänglig om något av följande villkor är uppfyllt:
>
> - Arbetsstatus är något annat än *öppen* eller *pågår*.
> - Ett behållar-ID associeras med arbets-ID. (En behållare kan inte delas upp på ett systematiskt sätt, eftersom den kräver fysiska åtgärder.)
> - Arbetet associeras med ett kluster.
> - Arbetsordertypen är något annat än någon av följande typer:
>
>    - Försäljningsorder
>    - Råmaterialhämtning
>    - Överför leverans
>
> - Arbetet håller på att delas av en annan användare. Om du försöker öppna delningssidan för arbete som redan delas av en annan användare visas följande felmeddelande: "arbetet med ID \#\#\#\# håller på att delas. Försök igen om några minuter. Kontakta en arbetsledare om du fortsätter att få det här meddelandet".

Ett nytt arbetsblockerande skäl *Dela arbete* anger när arbets-ID håller på att delas. Den visas både på sidan **Dela arbete** och i mobilappen för distributionslagerhantering om en användare försöker köra arbetet. När spärrningsorsaker används ändras namnet på fältet **spärrad påfyllnad** från arbets-ID till **spärrat**.

## <a name="initiate-a-work-split"></a>Starta en arbetsdelning

Funktionen lägger till en ny sida **delad arbete** där användarna kan dela upp arbetsrader från arbets-ID. När sidan öppnas visas rader med arbetsstatus *öppen* och som är tillgängliga för delning. I åtgärdsfönstret, välj **Dela arbete** för att bearbeta det valda arbetet.

Om du vill dela arbete följer du stegen nedan.

1. Öppna en av följande arbetssidor:

    - **Arbetsdetaljer** (**Lagerstyrning \> Arbete \> Arbetsdetaljer**)
    - **Allt arbete** (**Lagerstyrning \> Arbete \> Allt arbete**)

1. Välj ett arbets-ID som du vill dela i rutnätet. Fältet **arbetsordertyp** måste ha ett av följande värden:

    - Försäljningsorder
    - Råmaterialhämtning
    - Överför leverans

1. I åtgärdsfönstret, på fliken **Arbete**, i gruppen **Arbete**, väljer du **Dela arbete**.

    Sidan **Dela arbete** visas och visar de arbetsrader som är öppna och som är tillgängliga för delning. Som standard visas endast tillgängliga arbetsrader. Om du vill visa alla rader för arbets-ID (till exempel rader med arbetstyp *Placera*), välj **Visa alla rader** ovanför rutnätet.

    Följande meddelande visas: "användarna kan inte bearbeta rader i arbetet förrän du har slutfört delningen och stängt sidan".

    Fältet **Arbetsblockerande skäl** för aktuellt arbete kommer att anges till *Delat arbete* och arbetet blockeras. 

    ![Spärrningsorsak.](media/Blocking_reason.png "Spärrningsorsak")

1. Markera de rader som du vill ta bort från aktuellt arbets-ID och lägg till i ett nytt arbets-ID. Då inträffar följande händelser:

    - När du delar upp arbetet annulleras den markerade raden eller raderna från det ursprungliga arbets-ID och kopieras sedan till ett nytt arbets-ID.
    - Den befintliga arbetsmallstrukturen och placeringens plats (och även framtida plocknings-/placeringspar) bevaras. Värden för följande arbets-ID-fält kopieras från original arbetet till det nya arbetet:

        - Last-ID
        - Leverans-ID
        - Typ av arbetsorder
        - Ordernummer
        - Site
        - Lagerställe
        - Arbetsprioritet
        - ID för arbetspool
        - Påfyllnads-ID
        - Nummer för att skapa arbete

    - Följande fält kopieras inte till det nya arbets-ID:

        - **Arbets-ID** – ett nytt arbets-ID skapas från en nummerserie.
        - **Arbetsstatus** – detta fält är inställt på *öppen*.
        - **Låst av** – det här fältet ställs från början till tom.
        - **Mål ID-nummer** – detta fält lämnas tomt.
        - **Skapat datum och tid** – fältet ställs in på aktuellt datum och aktuell tid.
        - **Spärrad påfyllnad/fryst** – det här fältet har omberäknats för det ursprungliga arbets-ID och det nya arbets-ID.

1. Klicka på **Dela arbete** i åtgärdsfönstret.

När arbetet delas upp visas följande meddelande: "bearbetningsåtgärd - dela arbete". Även om det här meddelandet visas kan du avbryta åtgärden genom att välja **Avbryt** i meddelanderutan.

Om kryssrutan **Visa alla rader** är avmarkerad visas inte längre den rad som delades och annullerades i rutnätet. Om kryssrutan är markerad bör du se att värdet i fältet **Arbetsstatus** för den raden har ändrats till *Annullerat*.

Följande meddelande visar att det nya arbets-ID har skapats: "arbete \#\#\#\# har skapats genom att dela från ursprungligt arbete \#\#\#\# ."

Andra arbetsrader från det ursprungliga arbets-ID (t.ex. *placera* rader) justeras efter behov för att återspegla de arbetsrader som har annullerats. Om det ursprungliga arbets-ID t.ex. har raden *placera* för kvantiteten 15 och rader *plocka* med en total kvantitet på 10 har annullerats, kommer den nya kvantiteten *placera* i det ursprungliga arbets-ID att vara 5.

Det nya arbetet tilldelas inte omedelbart till någon användare. Du kan dock tilldela den till en användare vid behov genom att använda standardfunktionerna på sidan **arbetsuppgifter**.

> [!IMPORTANT]
> Du kan bara dela arbets-ID som innehåller två eller flera tillgängliga arbetsrader. Om du väljer **dela arbete** när det bara finns en arbetsrad visas följande felmeddelande: "minst en arbetsrader måste finnas kvar på det ursprungliga arbetet". I det här fallet görs ingen delning.

## <a name="finish-a-work-split"></a>Avsluta en arbetsdelning

För att slutföra delningsarbetet måste spärrningsorsak *Dela arbete* tas bort. Det finns två sätt att slutföra detta steg:

- Användaren som delar upp arbetet stänger sidan **Dela arbete** genom att välja knappen **Stäng** (**X**) i det övre högra hörnet. När sidan stängs tas blockeringsorsaken till det *delade arbetet* bort. Det *spärrade* tillståndet för det här arbetet kommer att omberäknas och, om det inte finns några återstående spärrningsorsaker för det här arbetet, kommer arbetet att avblockeras.
- Alla användare öppnar arbets-ID och väljer knappen **Avbryt arbetssession** för arbete i åtgärdsfönstret. Spärrningsorsak *Delat arbete* kommer att tas bort och *Blockerat* tillstånd för det här arbetet kommer att omberäknas, precis som **Delat arbete** är stängd.

När blockeringsorsaken *Delat arbete* tas bort kan arbetet köras på den mobila enheten, förutsatt att **Blockerat** tillstånd är inställt på *Nej* på arbets-ID.

## <a name="user-blocking-on-the-warehouse-management-mobile-app"></a>Användarblockering i mobilappen för distributionslagerhantering

Om du försöker använda mobilappen för distributionslagerhantering för att köra plockningsarbete mot ett arbets-ID som redan delas av en annan användare visas följande felmeddelande: "arbetet med ID \#\#\#\# håller på att delas. Om du får detta meddelande väljer du **Avbryt**. Därefter kan du fortsätta att bearbeta annat arbete.

## <a name="other-blocked-operations"></a>Andra blockerade operationer

Alla operationer som ändrar arbetsrader, arbetslagertransaktioner eller lagerpåfyllnadslänkar som är relaterade till arbete som delas kommer att misslyckas, och följande felmeddelande visas: "arbetet med ID håller \#\#\#\# just nu på att delas."


[!INCLUDE[footer-include](../../includes/footer-banner.md)]