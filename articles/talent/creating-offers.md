---
title: Skapa, godkänna och signera erbjudanden
description: Det här avsnittet beskriver hur du skapar, godkänner och registrerar ett erbjudande för en sökande med Dynamics 365 for Talent.
author: josaw
manager: AnnBe
ms.date: 02/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-10-19
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 5ad7ce1e089d2a8b5c52e7cd01bb3d89070004b1
ms.sourcegitcommit: ea17d2e35c24a141c20ab429897eebf9fa186f61
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/26/2019
ms.locfileid: "768915"
---
# <a name="creating-approving-and-signing-offers"></a>Skapa, godkänna och signera erbjudanden

[!include[banner](../includes/banner.md)]

I de flesta fall måste förberedande av ett erbjudandepaket för en sökande ske mycket snabbt.
Med hjälp av mallarna som skapats av Attract administratören kan tiden och insatsen minskas för de som skapar erbjudandet för att förbereda och skicka erbjudanden till en sökande.

## <a name="create-an-offer"></a>Skapa ett erbjudande

När programmet Erbjudandehantering aktiveras kan alla användare som har rollen anställande chef eller rekryterare förbereda ett erbjudandepaket för kandidaten. Gör följande om du vill förbereda ett erbjudande.

1.  Navigera till jobbet och kandidatens ansökning som du skapar erbjudandet för.

1.  Gå till **erbjudandefas** och på **förbered erbjudande**.

    Du kommer att omdirigeras till erbjudandeprogrammet där du kan se sökande med statusen **Ny**. Du kan också se andra erbjudanden som du bidrar till, antingen som en upphovsman eller godkännare.

1.  Klicka på **förbered erbjudande**. 
    
    Du kommer att se ett urval av olika erbjudandepaket som har gjorts tillgängliga av administratören.

1.  Välj ett paket och klicka på **Klar** för att börja förbereda erbjudandet.

    Erbjudandepaketmallen laddas med motsvarande jobb och information om kandidaten fylls i erbjudandet.

1.  Alla platshållare för erbjudandedata som ingår i erbjudandepaketet visas på landningssidan. Du kan fylla i alla värden över paketet på den här sidan.

    På landningssidan kan du se alla erbjudandedokumentmallar som ingår i paketerbjudandet.

1.  Nu kanske du kan redigera innehållet i erbjudandet, beroende på hur mallen har konfigurerats av administratören.

1.  Om du behöver ta bort dokument som markerats som inte obligatoriska kan du göra detta.

1. När alla platshållare för erbjudandedata har fyllts i klickar du på **spara** om du vill spara ett utkast av erbjudandet.

>[!NOTE]
> När utkast har sparats kan du ta bort erbjudandets utkastversion eller välja en ny paketmall om det behövs.


## <a name="approve-an-offer"></a>Godkänn ett erbjudande

De flesta erbjudanden måste gå igenom någon godkännandeprocess för att försäkra sig om erbjudandet uppfyller kraven. Om ett erbjudande inte uppfyller standarderna, till exempel om den som skapat erbjudandet inte följde reglerna för erbjudandedata och åsidosatte värdena i erbjudandet, ska godkännandeprocessen bestämmas. Gör följande om du vill skicka ett erbjudande till godkännande.

1.  När erbjudandet är i utkastform kan du lägga till godkännare på de **godkännarpanel**. 
    >[!NOTE]
    > Anställande chefer läggs som standard till som godkännare. Du kan välja alla användare från din organisation som godkännare för erbjudandet.

1.  Tilldela godkännare i en sekventiell metod eller en parallellt metod för godkännande om det behövs. Det här alternativet är bara tillgängligt om det konfigurerades av administratören.
    >[!NOTE]
    > Om godkännandeprocessen är sekventiell, kan du redigera sekvensen av godkännare om det behövs.

1.  När du är kan klar med definition av godkännandekedjan kan du redigera innehållet i e-postmeddelandet med godkännande och sedan skicka det till en godkännare. Klicka på **Skicka till godkännare**.
    >[!NOTE]
    > Om erbjudandet inte är standard, måste du ange en motivering.

1.  Om den som har skapat erbjudandet väljer att hoppa över en godkännare, kan de ange en anteckning och gå vidare till nästa godkännare.

Godkännare får e-post där de ombeds att godkänna erbjudandet. De kan klicka på länken i e-postmeddelandet för att öppna erbjudandet, granska hela erbjudandepaketet och antingen godkänna eller skicka tillbaka det till den som har skapat erbjudandet. Godkännare av erbjudanden måste lägga till ytterligare en anteckning om de avvisar erbjudandetpaketet för ytterligare redigering. 

I fall där det inte finns en ny version av erbjudandet skapat före godkännaren agerar kommer godkännaren inte att kunna godkänna eller avslå erbjudandet.

## <a name="offer-versioning"></a>Versioner av erbjudandet 

När erbjudandet har godkänts eller skickats tillbaka för vidare redigering kan du välja alternativet **Aktivera redigering** för att skapa en ny version av erbjudandet. Den nya versionen av erbjudandet har alla datavärden för erbjudandet och listan över godkännare förs över från den senaste versionen. 

Godkännare kan växla mellan olika erbjudandeversioner om de har delat ut till dem. för godkännande. Dessutom kan godkännare eller skapare av erbjudandet välja att ta bort ett visst utkast av erbjudandet och gå tillbaka till föregående steg.


## <a name="send-an-offer-to-a-candidate"></a>Skicka ett erbjudandet till en kandidat 

När erbjudandet sparats, godkänts och är klart att skickas ut till kandidaten klickar du på **skicka till kandidaten**.

Det finns flera åtgärder du kan vidta innan du skickar erbjudanden till kandidaten.
-  Du kan visa listan över dokument som ingår i erbjudandepaket som skickas till sökande.

-  Du kan ange ett förfallodatum för erbjudandet. Sökande förväntas acceptera eller avböja erbjudandet före förfallodatum.  Sökande skickas en påminnelse 48 timmar innan erbjudandet löper ut.

-  Det kan finnas flera dokument som du vill inkludera i processen för godkännande av erbjudandet. Du har alternativet att lista krävd dokumenttyp.

- Alternativet e-signatur: det finns två sätt att koppla e-signaturleverantören av ditt val. Gå till **Användarinställningar** i **Erbjudande**, under **Anslutningar** och anslut till **Adobe Sign** eller **DocuSign**. Du kan också uppmanas att ansluta till sidan **Skicka erbjudanden till kandidat** om anslutningen inte redan upprättats baserat på användarinställningarna. E-signaturkontot behöver bara kopplas en gång. Samma användarlicens används för alla framtida erbjudandepaket som skickas av samma användare. 

### <a name="adobe-sign"></a>Adobe Sign
Om Adobe Sign valdes som den föredragna metoden för e-signering måste skapare av erbjudandet ansluta Adobe Sign-licensen i det här steget. 

### <a name="docusign"></a>DocuSign
Om DocuSign valdes som den föredragna metoden för e-signering måste skapare av erbjudandet ansluta DocuSign-licensen. När du har loggat in ansluts standardkontot och behörigheter som är kopplade till användarens DocuSign-profil till Talent Attract. 

-  Du kan visa och redigera e-postmallen efter behov.

När erbjudandet är klart och du klickar på **skicka till kandidaten**, får kandidaten ett e-postmeddelande att ett erbjudande väntar på granskning.

>[!NOTE]
> Om du använder Adobe Sign eller DocuSign och du får ett felmeddelande när erbjudandet skickades till kandidaten, försök koppla från och återansluta e-signaturens användarkonto från **användarinställningar**. Om problemet kvarstår kontaktar du vår support genom att använda länken **rapportera ett problem**.

## <a name="candidates-actions-after-receiving-an-offer"></a>Sökandes åtgärder efter att ha mottagit ett erbjudande

När sökande har meddelats att ett erbjudande delats med dem, kan de klicka på länken i deras e-post för att gå till programmets instrumentpanel och visa erbjudandet. Instrumentpanelen visar kandidaten alla aktiviteter som de behöver utföra.

1.  Om du vill visa erbjudandet och alla relaterade dokument, måste kandidaten klicka på **visa erbjudande**.

    Kandidater kan också hämta erbjudandepaket i zip.-format.

1.  För att acceptera erbjudandet måste kandidater klicka på **hoppa till signatur** för varje dokument som ingår i erbjudandepaketet.

1.  När alla dokument är individuellt signerade och godkända måste kandidaten slutföra godkännandeprocessen genom att klicka på **acceptera erbjudande** överst på sidan.

1.  För att avvisa erbjudandet måste kandidaten klicka på **avvisa erbjudandet** längst upp på sidan, välja en lämplig orsak, lägga till en kommentar och klicka på **avvisa**.

1.  När de har acceptera eller avvisat erbjudandet, kan kandidaten fortsätta att vara i erbjudandevyn eller gå tillbaka till programmets instrumentpanel.

1.  Om det fanns andra handlingar som begärs av godkännandeprocessen av erbjudandet måste kandidaten överföra nödvändiga dokument och tagga dem med krävd dokumenttyp.

1.  Den som har skapat erbjudandet meddelas när alla dokument har överförts och erbjudandepaketet har signerats.


## <a name="withdrawing-an-offer"></a>Återkalla ett erbjudande

Ett erbjudanden kan återkallas från en kandidat när som helst efter olika skäl. 
1.  Återkalla erbjudandet genom att klicka på ellips-knappen (**...**), och klicka sedan på **Återkalla erbjudandet**. 

2. Ett meddelande visas där du tillfrågas om sökande har kontaktats om ändring i status. Om sökande inte har kontaktats ännu, får du möjlighet att skicka ett e-postmeddelande till kandidaten med information om ytterligare åtgärder. 

   Erbjudandet kommer inte längre vara tillgängliga för sökande.


## <a name="closing-an-offer"></a>Stänga ett erbjudande 

När ett erbjudande har godkänts, avvisats eller återkallats och inga ytterligare åtgärder krävs, kan du stänga erbjudandet så att inga fler ändringar kan göras i erbjudandepaketet.
