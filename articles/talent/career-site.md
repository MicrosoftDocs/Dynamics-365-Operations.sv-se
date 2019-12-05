---
title: Ställ in din karriärwebbplats i Attract
description: Det här avsnittet innehåller en översikt över funktionen för kandidatorienterad karriärwebbplats i Microsoft Dynamics 365 Talent - Attract.
author: hasrivas
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: d4a1e7c19ccec6ae32e46ec7d58604b162418953
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832964"
---
# <a name="set-up-your-career-site-in-attract"></a>Ställ in din karriärwebbplats i Attract

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller en översikt över funktionen för kandidatorienterad karriärwebbplats i Microsoft Dynamics 365 Talent: Attract. Den förklarar även hur du ställer in denna funktion.

Attract ger en karriärwebbplats för olika miljöer i en klientorganisation. Om till exempel ett företag har en utvecklingsmiljö och en testmiljö kan en karriärwebbplats för utvecklingsmiljön tilldelas utvecklingsmiljön och en annan karriärwebbplats tilldelas testmiljön. Varje karriärwebbplats är helt isolerad och har en egen autentiseringsmekanism. Jobb och kandidatprofiler delas inte mellan karriärwebbplatser.

Som standard är karriärwebbplatsen offentlig. Kandidater kan därför visa alla jobb som markeras som externa utan att behöva logga in. Alla andra åtgärder kräver emellertid att kandidater loggar in.

## <a name="career-site-management"></a>Hantera karriärwebbplats

Om du vill ange värden för följande artiklar loggar du in på Attract som administratör och väljer **administratörscenter** på menyn **inställningar** (växelsymbol) och väljer sedan fliken **Företagsupplysningar**.

-   **Organisationsnamn** - organisationsnamnet visas i navigeringsfältet längst upp i karriärwebbplatsen. Genom att välja organisationsnamn kan kandidater gå till en sida som visar alla lediga jobb.

-   **Organisationslogga** - en bild av företagets logotyp visas längst upp till vänster på karriärwebbplatsen. Genom att välja logotypbild kan kandidater gå till en sida som visar alla lediga jobb.

    > [!NOTE] 
    > Logotypbilden som visas på karriärwebbplatsen har en fast höjd på 20 pixlar (px). Bilden som du lägger till i administratörscentret skalas så att den passar. Därför kan bredden ändras, beroende på bilden.
 
Om du vill ange värden för följande artiklar loggar du in på Attract som administratör och väljer **administratörscenter** på menyn **inställningar** (växelsymbol) och väljer sedan fliken **Hantera karriärwebbplats**.

-   **Sökmotoroptimering** - om aktiverad kommer alla offentliga jobb som publiceras på Attract karriärwebbplats att vara sökbara med hjälp av sökmotorer som Bing och Google. 

    > [!NOTE] 
    > Det kan finnas en fördröjning mellan aktivering av inställningen och sökresultaten som visas, beroende på sökfunktionen du använder.
    
-   **Villkor** - när de aktive ras måste alla kandidater godkänna organisationens villkor när de ansöker om ett jobb. Attract-administratören kan konfigurera sin egen godkännandetext samt länken till deras villkor. 

        
## <a name="career-site-urls"></a>URL för karriärwebbplats

Följande lista innehåller vanliga URL för karriärwebbplatser och hur du kommer åt dem.

-   **Karriärwebbplatsens startside-URL** - för att visa startsidan för karriärwebbplatsen, logga in i Attract som administratör och välj **administratörscenter** på menyn **inställningar** -och välj sedan fliken **Hantera karriärwebbplats**.

-   **Svars-URL för individuell jobbpublicering** - När du [publicerar ett externt jobb](Creating-jobs-Attract.md#postings) för första gången, kan du kopiera länken **Använd** från Attract. URL-adressen för den här länken är i följande format: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)

-   **Individuell jobbpublicerings-URL** - URL för jobbpubliceringen är en delsträng av svars-URL. Den består av allt upp genom jobbnumret. Därför är jobbpublicerings-URL:en för de föregående svars-URL [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)

## <a name="authentication-options"></a>Autentiseringsalternativ

Kandidater har följande inloggningsalternativ för en Attract karriärwebbplats:

-   Personligt konto:

    -   LinkedIn

    -   Microsoft

    -   Google

    -   Facebook

-   Jobb- eller skolkonto:

    -   Microsoft Azure Active Directory (Azure AD)

Azure AD-inloggning är endast avsedd för interna kandidater. Därför fungerar den endast för interna kandidater som utnyttjar deras Azure AD-autentiseringsuppgifter för företag. Till exempel vill en kandidat som för närvarande är anställd på Contoso, Ltd. ansöka om ett jobb i ett inte relaterat företag Alpine Ski House. I det här fallet kommer inloggningen att misslyckas om medarbetaren försöker använda hans eller hennes Azure AD-autentiseringsuppgifter från Contoso Ltd. 

Kandidater måste logga in med hjälp av Azure AD om jobbet som de visar eller ansöker endast annonseras som internt.

## <a name="create-and-maintain-a-profile"></a>Skapa och underhålla en profil

När kandidater loggar in på karriärwebbplatsen kan de välja **min profil** i navigeringsfältet längst upp på sidan om de vill skapa och underhålla sin profil.
Profilen innehåller personuppgifter, information om arbetserfarenhet, utbildningsuppgifter, dokument, länkar och information om kompetensuppsättningar. När en profil har skapats kan den användas till att ansöka om ett jobb som kandidaten är intresserad av. Profiler kan också hjälpa Attract att rekommendera rätt jobb till kandidater.

> [!NOTE]
> Om en kandidat använder ett e-post-ID för att logga in på någon av de autentiseringsproviders som anges ovan, kommer detta e-post-ID överföras som standard till kontaktens e-post-ID som är kopplat till profilen. Men detta kan ändras när som helst och är helt oberoende av den förra. Attract kommer alltid använder kontakters e-post-ID för att koppla till profilen för alla e-postmeddelanden.

## <a name="find-the-right-job"></a>Hitta rätt jobb

På listsidan för jobb kan kandidater söka efter ett visst jobb genom att ange sökvillkor. Sökfunktionen söker efter sökord i jobbtitlar och arbetsbeskrivningar och visar relevanta jobb som resultat. Kandidater kan filtrera resultaten när som helst baserat på plats för jobbet eller arbetsuppgifter.

Kandidater kan också visa en uppsättning av rekommenderade jobb på karriärwebbplatsen. Jobben som rekommenderas till en kandidat baseras på kandidatens tidigare ansökningar, profil och meritförteckningar.

> [!NOTE] 
> Jobbrekommendationer visas endast om minst 10 jobb publiceras på karriärwebbplatsen och om kandidaten har slutfört en profil.

Interna kandidater kan också se vem den anställande chefen och/eller rekryteraren är för ett jobb om de vill kontakta dessa medlemmar i anställningsteamet. Externa kandidater har emellertid ingen insyn i medlemmar av anställningsteamet för något jobb.

## <a name="contact-the-hiring-team"></a>Kontakta anställningsteamet
Endast interna kandidater kan kontakta anställningsteamet. Denna begränsning gäller för alla jobb, oavsett om de är endast interna eller har publicerats offentligt.

Kandidater kanske vill kontakta anställningsteamet för att uttrycka intresse i ett jobb som har publicerats eller lära sig mer om det. De kan kontakta någon av anställningsteamets medlemmar som visas (anställande chef eller rekryterare). De kan även bifoga en meritförteckning i meddelandet eller välja att återuppta en befintlig meritförteckning som de tidigare överfört som en del av sin profil.

När en intern kandidat väljer att kontakta anställningsteamets medlemmar skickar Attract ett e-postmeddelande till personer för kandidatens räkning. Samtidigt läggs kandidatens profil till i fasen **potentiella kandidater** om den fasen är tillgänglig för jobbet. Under fasen **potentiella kandidater** kan rekryterare eller anställande chefer visa kandidater som har kontaktat dem. De kan också granska kandidaters profiler och bjuda in potentiella kandidater att ansöka.

Kandidater kan ansöka om ett jobb som de redan har kontaktat anställningsteamets medlemmar om. När de har ansökt kan kandidaterna inte längre kontakta anställningsteamet via jobbwebbplatsen.

## <a name="apply-for-jobs"></a>Söka jobb

När kandidater hittar rätt jobb kan de ansöka om det med hjälp av knappen  **Ansök**  på sidan  **Jobbdetaljer**. Nu kan kandidater antingen skapa en ny profil eller gå igenom informationen i den befintliga profilen.
Kandidater kan också vid behov överföra en meritförteckning och sedan skicka in jobbansökningen.

### <a name="enable-applying-for-jobs-with-linkedin-profiles"></a>Aktivera ansökan om jobb med LinkedIn-profiler

Du kan göra det enkelt för kandidater att ansöka om din befattningar genom att konfigurera Attract för att de ska ansöka via LinkedIn.

> [!NOTE] 
> Du behöver en eller flera rekryterarlicenser från LinkedIn innan du kan tillåta att kandidater ansöker med LinkedIn.

1. Logga in på Attract som en administratör.
2. Välj knappen **inställningar** (växelsymbol) i det övre högra hörnet på sidan och välj sedan **administratörscenter**.
3. Välj fliken **LinkedIn-integration** och anslut sedan till ett LinkedIn Recruiter-konto.
4. I avsnittet **LinkedIn Recruiter System Connectintegration** väljer du **aktiverad** för inställningen **Ansök med LinkedIn**.

När du har aktiverat inställningen kan kandidater ansöka med hjälp av deras befintliga LinkedIn profildata. När kandidater ansöker genom att välja knappen **Ansök med LinkedIn** ombeds de att autentisera med LinkedIn om de inte redan är inloggade. Efter de har autentiserats ersätter deras LinkedIn-profil eventuella befintliga profildata som visas på ansökningssidan. Kandidater kan redigera informationen som behövs och sedan skicka in sin ansökan. Om en kandidat navigerar bort från sidan utan att ansöka om jobbet, uppdateras deras profildata inte i Attract.

## <a name="check-application-status"></a>Kontrollera ansökningsstatus

När kandidater ansöker om ett eller flera jobb, kan de välja **Ansökningar** i navigeringsfältet längst upp på sidan för att visa öppna och stängda ansökningar. När kandidater öppnar en av sina ansökningar, visas den aktuella fasen samt eventuella väntande uppgifter som de måste slutföra. Om en kandidat t.ex. måste ange möjliga datum för en personlig intervju visar sidan tillgängliga alternativ.

## <a name="internal-jobs"></a>Interna jobb

För närvarande visas jobb som markerats som interna och publicerade på Attract karriärwebbplatsen inte på karriärwebbplatsen. De är endast tillgängliga via den direkta **Ansöknings**-URL:en som kan kopieras från Attract-programmet.
