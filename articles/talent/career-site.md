---
title: "Funktionen för karriärwebbplats i Attract"
description: "Det här avsnittet innehåller en översikt över funktionen för kandidatorienterad karriärwebbplats i Microsoft Dynamics 365 for Talent - Attract. Den förklarar även hur du ställer in denna funktion."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: sv-se
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a>Funktionen för karriärwebbplats i Attract

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller en översikt över funktionen för kandidatorienterad karriärwebbplats i Microsoft Dynamics 365 for Talent - Attract. Den förklarar även hur du ställer in denna funktion.

## <a name="overview"></a>Översikt

Attract ger en karriärwebbplats för olika miljöer i en klientorganisation. Om till exempel ett företag har en utvecklingsmiljö och en testmiljö kan en karriärwebbplats för utvecklingsmiljön tilldelas utvecklingsmiljön och en annan karriärwebbplats tilldelas testmiljön. Varje karriärwebbplats är **helt isolerad** och har en egen autentiseringsmekanism. Jobb och kandidatprofiler delas inte mellan karriärwebbplatser.

Som standard är karriärwebbplatsen offentlig. Kandidater kan därför visa alla jobb som markeras som externa utan att behöva logga in. Alla andra åtgärder kräver emellertid att kandidater loggar in.

## <a name="career-site-management"></a>Hantera karriärwebbplats

Följande artiklar på karriärwebbplatsen styrs av inställningarna:

- **Organisationsnamn:** organisationsnamnet visas i navigeringsfältet längst upp i karriärwebbplatsen. Genom att välja organisationsnamn kan kandidater gå till en sida som visar alla lediga jobb.
- **Organisationslogga:** en bild av företagets logotyp visas längst upp till vänster på karriärwebbplatsen. Genom att välja logotypbild kan kandidater gå till en sida som visar alla lediga jobb.

Om du vill ange värden för organisationsnamn och logotyp loggar du in på Attract som administratör och väljer **administratörscenter** på menyn **inställningar** (växelsymbol) och väljer sedan fliken **Företagsupplysningar**.

> [!NOTE]
> Logotypbilden som visas på karriärwebbplatsen har en fast höjd på 20 pixlar (px). Bilden som du lägger till i administratörscentret skalas så att den passar. Därför kan bredden ändras, beroende på bilden.

## <a name="career-site-url"></a>Webbadress till karriärwebbplats

När du [bokför ett externt jobb](./Creating-jobs-Attract.md#postings) för första gången, kan du kopiera länken **Använd** från Attract-programmet. URL-adressen för den här länken är i följande format: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`

URL-adressen till karriärwebbplatsen är en delsträng av URL:en **Använd**. Den består av allt upp genom företagsnamnet. Därför är karriärwebbplatsens URL för de föregående webbadressen för **Använd** `https://jobs.talent.dynamics.com/jobs/<company_name>/`.

## <a name="authentication-options"></a>Autentiseringsalternativ

Kandidater har följande inloggningsalternativ för en Attract karriärwebbplats:

- Personligt konto:

    - LinkedIn
    - Microsoft 
    - Google
    - Facebook

- Jobb- eller skolkonto:

    - Microsoft Azure Active Directory (Azure AD)

Azure AD-inloggning är endast avsedd för interna kandidater. Därför fungerar den endast för interna kandidater som utnyttjar deras Azure AD-autentiseringsuppgifter för företag. Till exempel vill en kandidat som för närvarande är anställd på Contoso, Ltd. ansöka om ett jobb i ett inte relaterat företag Alpine Ski House. I det här fallet kommer inloggningen att misslyckas om medarbetaren försöker använda hans eller hennes Azure AD-autentiseringsuppgifter från Contoso Ltd.

## <a name="create-and-maintain-a-profile"></a>Skapa och underhålla en profil

När kandidater loggar in på karriärwebbplatsen kan de välja **min profil** i navigeringsfältet längst upp på sidan om de vill skapa och underhålla sin profil. Profilen innehåller personuppgifter, information om arbetserfarenhet, utbildningsuppgifter, dokument, länkar och information om kompetensuppsättningar. När en profil har skapats kan den användas till att ansöka om ett jobb som kandidaten är intresserad av. Profiler kan också hjälpa Attract att rekommendera rätt jobb till kandidater.

## <a name="find-the-right-job"></a>Hitta rätt jobb

På listsidan för jobb kan kandidater söka efter ett visst jobb genom att ange sökvillkor. Sökfunktionen söker efter sökord i jobbtitlar och arbetsbeskrivningar och visar relevanta jobb som resultat. Kandidater kan filtrera resultaten när som helst baserat på plats för jobbet eller arbetsuppgifter.

Kandidater kan också visa en uppsättning av rekommenderade jobb på karriärwebbplatsen. Jobben som rekommenderas till en kandidat baseras på kandidatens tidigare ansökningar, profil och meritförteckningar.

> [!NOTE]
> Jobbrekommendationer visas endast om minst 10 jobb publiceras på karriärwebbplatsen och om kandidaten har slutfört sin profil.

## <a name="apply-for-jobs"></a>Söka jobb

När kandidater hittar rätt jobb kan de ansöka om det med hjälp av knappen **Ansök** på jobbets detaljsida. Nu kan kandidater antingen skapa en helt ny profil eller gå igenom informationen i den befintliga profilen. Kandidater kan också vid behov överföra en meritförteckning och sedan skicka in jobbansökningen.

## <a name="check-application-status"></a>Kontrollera ansökningsstatus

När kandidater ansöker om ett eller flera jobb, kan de välja **Ansökningar** i navigeringsfältet längst upp på sidan för att visa öppna och stängda ansökningar. När kandidater öppnar en av sina ansökningar, visas den aktuella fasen samt eventuella väntande uppgifter som de måste slutföra. Om en kandidat t.ex. måste ange möjliga datum för en personlig intervju visar sidan hans eller hennes alternativ.

## <a name="internal-jobs"></a>Interna jobb

För närvarande visas jobb som markerats som interna och publicerade på Attract karriärwebbplatsen inte på karriärwebbplatsen. De är endast tillgängliga via den direkta **Ansöknings**-URL:en som kan kopieras från Attract-programmet.

