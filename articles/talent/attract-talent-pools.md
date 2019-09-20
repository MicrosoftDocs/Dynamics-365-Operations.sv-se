---
title: Skaffa kandidater med talangpooler i Microsoft Dynamics 365 for Talent - Attract
description: Det här avsnittet beskriver hur du skapar och konfigurerar talangpooler i Microsoft Dynamics 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/28/2019
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
ms.author: anbichse
ms.search.validFrom: 2018-22-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 98b93f69c4f4c8ca6c9a0fc2530578afed4b967c
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741877"
---
# <a name="source-candidates-with-talent-pools"></a>Skaffa kandidater med talangpooler

[!include[banner](../includes/banner.md)]


Rekryterare och anställande chefer kan ordna sina kandidater med funktionen talangpooler i Attract. Talangpooler kan hjälpa dig att hålla reda på och kommunicera med kandidater som söker jobb i ditt företag.

## <a name="create-and-share-a-talent-pool"></a>Skapa och dela en talangpool

Alla användare med rollen rekryterare, anställande chef eller Attract-administratör kan skapa talangpooler. Ägaren till en talangpool kan också dela poolen med andra användare så att användargrupper, särskilt rekryterare kan titta på en delad pool av kandidater.

Deltagare i en talangpool kan visa listan med kandidater i poolen. De kan också lägga till kandidater till poolen eller ta bort kandidaten från den.

Följ instruktionerna nedan för att skapa och dela en talangpool.

1. På Attract hemsida, i navigeringsfältet till vänster väljer du **Talangpooler**.

    Fliken **Mina talangpooler** visar alla talangpooler som du har tillgång till, med information om varje. Informationen omfattar ägare till poolen och antal kandidater i den.

1. I det övre högra hörnet av sidan väljer du **+ Ny** för att öppna dialogrutan **skapa talangpool**.
1. Ange ett unikt namn för talangpoolen.
1. Om du vill lägga till personer som deltagare i poolen, hitta namnen med hjälp av personväljaren och lägg till dem i listan. Du kan endast dela en talangpool med användare som har rollen rekryteraren, anställande chef eller Attract-administratör.
1. Välj **Lägg till** för att skapa talangpool.
     > [!NOTE]
     > Alternativt kan du lägga till deltagare en talangpool när du har skapat den. Du kan också hantera åtkomst till en talangpool. Du kan exempelvis återkalla en användares åtkomst till talangpoolen.
     > - För att lägga till deltagare till en befintlig talangpool som du äger, på fliken **Mina talangpooler** i det övre högra hörnet på talangpoolkortet väljer du knappen med tre punkter (**...**), och väljer sedan **redigera**. Hitta personer med hjälp av personväljaren och lägg till dem i listan. 
     > - För att återkalla användarens tillgång till talangpoolen, i övre högra hörnet av talangspoolkortet, välj ellips-knappen (**...**) och välj sedan **redigera**. På fliken **hantera åtkomst**, välj knappen för papperskorgen bredvid användaren.

6. Välj **uppdatera** för att slutföra och spara åtgärden.

> [!NOTE]
> Organisationen måste ha tillägget för omfattande anställning för att skapa mer än en talangpool.

## <a name="add-and-remove-candidates"></a>Lägga till och ta bort kandidater

Ägare och medarbetare till talangpoolen kan lägga till kandidater till talangpoolen, visa kandidaterna iden och ta bort kandidater från den.

1. På fliken **Mina talangpooler** väljer du en talangpool så att den öppnas.

    En förteckning över kandidater som ingår i talangpoolen visas.

1. Lägg till kandidater till talangpoolen, markera **+ Ny** i det övre högra hörnet om du vill öppna dialogrutan **Lägg till kandidat** och gör sedan något av följande.

    - Om du vill lägga till en intern kandidat, kan du söka efter personens efter e-postadress. Efter en lyckad sökning fylls kandidatens e-postadress, förnamn och efternamn i. Om du har kandidatens meritförteckning eller några relaterade dokument om kandidaten kan du överföra dem nu. Välj sedan **Lägg till** för att lägga till kandidaten till talangpoolen.
    - Om du vill lägga till en extern kandidat kan du manuellt ange hans eller hennes e-postadress, förnamn och efternamn. Om du har kandidatens meritförteckning eller några relaterade dokument kan du överföra dem nu. Välj sedan **Lägg till** för att lägga till kandidaten till talangpoolen.
    - Om du vill lägga till flera kandidater kan du välja fliken **Från Excel**. Du kan sedan hämta lämplig Microsoft Excel-mall, ange informationen för kandidaterna, spara Excel-kalkylbladet och överföra den till programmet.

        Om det finns några fel i kalkylbladet får du meddelanden om felen. Du kan sedan åtgärda felen och försöka att överföra kalkylbladet igen. När inga fler fel hittas, markerar du **Lägg till** för att överföra kalkylbladet. Kalkylbladet bearbetas i bakgrunden och du får ett meddelande när kandidaterna har lagts till i talangpoolen.

1. Du tar bort en befintlig kandidat från talangpoolen i kolumnen **åtgärd**, väljer knappen för papperskorgen för den här kandidaten.

## <a name="search-and-view-candidate-profiles"></a>Söka och visa kandidatprofiler

> [!NOTE] 
> Den här funktionen är för närvarande i förhandsgranskning. Om du vill prova den måste du [aktivera den i Attract administrationsinställningar](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature). 

Talangpooler låter dig visa kandidaters profil, LinkedIn-information, relaterade dokument och ansökningshistorik. Du kan söka igenom hela databasen över alla kandidater till någon talangpool, inklusive stängda och aktiva sökande.

>[!NOTE]
> När du lägger till nya kandidater eller sökande kan nya tillägg ta upp till 15 minuter att indexeras för sökning.

Med den förbättrade sökfunktionen kan du söka igenom alla kandidatens dokument och filtrera efter silvermedaljer, källor, färdigheter, utbildning och mycket mer. I tidigare versioner var du tvungen att ange enheten du vill söka igenom. Attract kan nu söka alla kandidatrelaterade fält och rangordna resultat.

1. Om du vill starta en ny sökning i kandidatdatabasen anger du texten som du vill söka efter i sökrutan på fliken **talangpooler**. 

Du kan skriva kandidatens namn eller andra attribut du söker. Om du vill avgränsa attribut använder du blanksteg.

Du kan begränsa reslutaten genom att ändra sökfrågan eller genom att använda smarta filter till vänster på sidan.

Sökresultatet visarmarkeringar för olika attribut som matchade sökfrågan. Markera den kandidat som du är intresserad av för att visa deras profil.

### <a name="syntax-highlights"></a>Syntaxmarkeringar 

| Operatör | Användning                                                      | Exempel              |
|----------|------------------------------------------------------------|----------------------|
| \*       | Söka efter delsträngar; kan användas för att returnera alla poster | Indata: Mi\* <br></br> Resultat: Alla poster som innehåller fält som börjar med ”Mi”, t.ex. Microsoft, Micro system, Midtown-företag eller Middleton <br></br>Indata: \* <br></br> Resultat: Alla poster i databasen |
| “”       | Söker efter en exakt matchning                                | Indata: ”Microsoft” <br></br> Resultat: Alla poster som innehåller ”Microsoft”                    |

>[!WARNING]
> Stäng inte av relevanssökning efter din Common Data Service-instans. Detta kommer att inaktivera sökupplevelsen i Attract.

Alla användare har en gemensam vy över kandidatprofiler. Fliken **profil** visar all information om kompetenser, arbetserfarenhet och utbildning som kandidaten har tillhandahållit som en del av sin ansökan med hjälp av karriärportalen.

- Du kan visa kontaktinformation för kandidaten. Du kan också redigera eller uppdatera informationen som du behöver genom att använda knappen **redigera detaljer**.

- Du kan visa kandidatens historik och hela ansökningshistoriken. Du kan visa alla jobb som kandidaten har ansökt om i organisationen och status för dessa ansökningar. Om du är en del av jobbets anställningsteam kan du välja **visa** för att titta på ansökningen i detalj.

- Fliken **dokument** visar alla handlingar som kandidaten har lagt till från hans eller hennes profil eller under jobbansökningar. Du kan använda den här fliken för att hantera kandidatens meritförteckningar, följebrev, portföljarbete, och så vidare. Du kan också använda den här fliken för att lägga till dokument.

    Om du vill visa ett dokument markerar du dokumentnamnet i dokumentlistan. Du kan visa Microsoft Word-dokument i programmet med Microsoft Office 365. Du kan också hämta dokument på den lokala datorn med hjälp av alternativet **hämta** för varje dokument.

- Fliken **LinkedIn** visar kandidatens LinkedIn-information. Om du vill använda den här fliken måste du ansluta ditt LinkedIn-konto i användarinställningarna och din miljös LinkedIn Recruiter-anslutning måste skapas. Mer information finns i [Anskaffning med LinkedIn Recruiter](./attract-linkedin-recruiter.md).

> [!NOTE]
> Endast kandidater kan uppdatera färdigheter, utbildningshistorik och arbetserfarenhet.

## <a name="add-candidates-from-a-talent-pool-to-a-job"></a>Lägg till kandidater från en talangpool till ett jobb

Från sökresultaten eller en talangpool kan du trycka en kandidat till alla aktiva jobb som du anställer för. Följ anvisningarna för att trycka en kandidat till ett visst jobb.

1. Hitta kandidater genom att använda sökfunktionen och öppna hans eller hennes profil. Alternativt öppnar du talangpoolen från fliken **Mina talangpooler**, söker efter kandidaten i talangpoolen och öppnar hans eller hennes profil.

1. Markera **Lägg till jobb** på kandidatens profil i det övre högra hörnet. 
     
     En lista med jobb som tillhör anställningsteamet, antingen som en rekryterare eller anställande chef visas.

1. Välj jobbet som kandidaten ska läggas till och välj sedan **Lägg till**. Du kan också söka efter jobbet med hjälp av sökfältet högst upp i dialogrutan **Lägg till kandidat till jobb**.

    Om prospektering aktiverades för jobbet läggs kandidaten till i fasen **Potentiell kandidat**.

    Om prospektering inte aktiverades för jobbet läggs kandidaten till i fasen **Ansök**. Beroende på jobbkonfigurationen kan kandidaten även få ett e-postmeddelande där de kan se sin ansökan.

## <a name="add-candidates-from-a-job-to-a-talent-pool"></a>Lägg till kandidater från ett jobb till en talangpool

Ofta väljs inte flera bra kandidater till ett jobb, men du vill inte tappa bort dem. I detta fall kanske du vill lägga till kandidaten till en talangpool så att du kan bjuda in dem att ansöka om andra kommande jobb.

1. Gå till det jobb som du vill lägga till en kandidat från.

1. Välj kandidaten och öppna hans eller hennes ansökan.

1. På ansökningssidan väljer du **Lägg till i talangpool**. En lista över talangpooler som du har tillgång till visas.

1. Välj eller sök efter talangpool och välj sedan **Lägg till** för att lägga till kandidater till talangpoolen.
