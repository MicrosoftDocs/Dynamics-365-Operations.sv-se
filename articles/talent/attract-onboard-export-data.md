---
title: Exportera data från Attract och Onboard
description: Exportera data från Dynamics 365 Talent - Attract och Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: acdd93637385246f9c5c652cccdf2cbfb263cc33
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/23/2020
ms.locfileid: "2975944"
---
# <a name="export-data-from-attract-and-onboard"></a>Exportera data från Attract och Onboard

[!include [banner](includes/banner.md)]

Som meddelas [Ta Dynamics 365 Talent: Attract och Dynamics 365 Talent: Onboard-appar ur bruk](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), tar vi Dynamics 365 Talent: Attract och Dynamics 365 Talent: Onboard ur bruk den 1 februari 2022. För att hjälpa till vid migreringen till en annan produkt tillhandahåller de båda apparna dataexportfunktioner.

## <a name="export-data-from-attract"></a>Exportera data från Attract

Du kan exportera data utan att begränsa åtkomsten till din miljö. Du kanske vill göra detta i testningssyfte eller för att förstå vår datastruktur. När du är redo att migrera ska du begränsa åtkomsten till din locka miljö med hjälp av instruktionerna efter den här proceduren. Var noga med att exportera data. 

1. Gå till [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. Under **Dataexport**, välj **Begär en dataexport**.

   ![[Begär en dataexport från Attract](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. När meddelanderutan **Din begäran behandlas** visas, välj **OK**. Dataexporten kan ta upp till 20 minuter, beroende på hur stor exporten är.

4. När exporten är klar väljer du knappen **Hämta** bredvid. 

   >[!NOTE]
   >All dataexport är tillgänglig i sju dagar, varvid länken **hämta** går ut.</br>
   
Hämtningen innehåller en zip-fil med dina Attract-data, inklusive följande mappar:

| Mappnamn | Beskrivning |
| --- | --- |
| Administratörsinställningar | Konfigurationer av Attract administrationscenter. |
| Kandidater | Alla kandidater som har lagts till i jobb eller talangpooler. |
| E-postmallar | Alla e-postmallar som har konfigurerats för miljön. |
| Mallar för jobberbjudandepaket | Alla jobberbjudandepaket som har skapats samt tillhörande konfigurationer. |
| Regeluppsättningar för jobberbjudande |  Alla regeluppsättningsfiler som har överförts för erbjudandehantering. |
| Mallar för jobberbjudande | Alla dokumentmallar för jobberbjudanden som skapats för miljön. |
| Lediga jobb | Alla skapade jobb. Borttagna jobb exporteras inte. Undermapparna innehåller kandidatansökningar, med undermappar för kandidatansökningars bilagor och erbjudandepaket, där det är tillämpligt. |
| Mallar för lediga jobb | Mallar för jobbearbetning som har konfigurerats för miljön. |
| Talangpooler | Alla skapade talangpooler, deras deltagarlistor och listor över kandidater för talangpooler. |
| Arbetare | Lista över alla arbetare som finns i miljön, plus deras roller. |
| (rotmapp) | En JSON-schemafil som beskriver fälten i datastrukturen. |

### <a name="restrict-access-to-attract"></a>Begränsa åtkomsten till Attract

När du är redo att migrera kan du hindra icke-administratörer från att komma åt din Attract-miljö och exportera dina data.

>[!IMPORTANT]
>Att begränsa åtkomsten till din Attract-miljö är permanent och kan inte ångras. Om du vill att andra användare än administratörer ska kunna fortsätta att komma åt din miljö hoppar du över det här steget.

1. Gå till [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. Om du vill hindra icke-administratörer från att komma åt din Attract-miljö, under **begränsa åtkomst till den här appen** väljer du **begränsa åtkomst nu**. Om du begränsar åtkomsten avpublicerar du även aktiva jobb som har bokförts.

   ![[Begränsa åtkomsten för de som inte är administratörer till Attract](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. Om varningen **Detta är en permanent ändring**, välj **begränsa åtkomsten** för att permanent begränsa användare som inte är administratörer från denna miljö. Om du inte är klar med det här steget väljer du **Avbryt**.

   ![[Varning att begränsa åtkomsten är permanent ändring](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   >Administratörer kan fortsätta att komma åt sidorna för dataexport och personrapport när du har begränsat åtkomsten till din Attract-miljö.

## <a name="export-data-from-onboard"></a>Exportera data från Onboard

När du är klar kan du hämta mallar, handböcker och kandidatdata från Onboard.

1. Gå till [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).

2. Under **Dataexport**, välj **Begär en dataexport**. 

   ![[Begär en dataexport från Onboard](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. När meddelanderutan **Din begäran behandlas** visas, välj **OK**. Dataexporten kan ta upp till 20 minuter, beroende på hur stor exporten är.

4. När exporten är klar väljer du knappen **Hämta** bredvid. 

   ![[Hämta dataexport från Onboard](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   >Dataexporten är tillgänglig i sju dagar. Efter sju dagar går länken **hämta** ut och du måste begära en ny export om du behöver hämta dina data igen. När du startar en ny dataexport upphör alla befintliga hämtningar att gälla när den nya exporten har lyckats.

Filen hämta är en zip-fil som innehåller:

- En **mall**-mapp som innehåller dina Onboard-mallar i Word-dokument.

- En **Guider**-mapp som innehåller dina Onboard-guider i Word-dokument.

## <a name="see-also"></a>Se även

[Ta Dynamics 365 Talent: Attract och Dynamics 365 Talent: Onboard-appar ur bruk](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)