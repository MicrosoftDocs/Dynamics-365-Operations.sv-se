---
title: Ställa in och använda den utökade inloggningskapaciteten
description: I denna artikel beskrivs hur du konfigurerar och utökar inloggningsförmågan hos Microsoft Dynamics 365 Commerce-kassaprogrammet (POS).
author: boycezhu
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.industry: Retail
ms.search.form: RetailFunctionalityProfile
ms.openlocfilehash: e2fc39b1b7fb34f49c061dcc324c28cf5a89277c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283706"
---
# <a name="set-up-and-use-the-extended-logon-capability"></a>Ställa in och använda den utökade inloggningskapaciteten

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar och utökar inloggningsförmågan hos Microsoft Dynamics 365 Commerce-kassaprogrammet (POS).

Cloud POS (CPOS) och Modern POS (MPOS) har en utökad inloggningskapacitet som gör att butiksarbetare loggar in i kassaprogrammet genom att skanna en streckkod eller dra ett kort med hjälp av en kortläsare (MSR).

## <a name="set-up-extended-logon"></a>Ställa in utökade inloggning

Ställ in utökad inloggning för kassaregister i en butik genom att följa stegen nedan.

1. I Commerce headquarters, gå till **Butik och Handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**. 
2. Välj den funktionsprofil som är kopplad till butiksbutiken i det vänstra navigeringsfönstret.
3. I snabbfliken **Funktioner**, under **Ytterligare inloggningsautentisering alternativ**, ange följande alternativ till **Ja** eller **Nej** efter behov.

    - **Streckkodsinloggning för personal** – Ange det här alternativet till **Ja** om du vill att medarbetarna ska logga in i kassan genom att skanna en streckkod. 
    - **Streckkodsinloggning kräver lösenord** – Ange det här alternativet till **Ja** om du vill att medarbetarna ska ange lösenord när de loggar in i kassan genom att skanna en streckkod.
    - **Personalkortsinloggning** – Ange det här alternativet till **Ja** om du vill att medarbetarna ska logga in i kassan genom att svepa ett kort.
    - **Personalkortsinloggning kräver lösenord** – Ange det här alternativet till **Ja** om du vill att medarbetarna ska ange lösenord när de loggar in i kassan genom att svepa ett kort.

Streckkoden eller kortet är kopplat till autentiseringsuppgifter som kan tilldelas en arbetare. Autentiseringsuppgifterna måste ha minst sex tecken. Strängen som innehåller de första fem tecknen måste vara unik och betraktas som ett *autentiserings-ID* som används för att söka efter en arbetare. Återstående tecken används för säkerhetsverifiering. Du har till exempel två kort, varav en har autentiseringsuppgifterna 12345DGYDEYTDW och varav en har autentiseringsuppgifterna 12345EWUTBDAJH. Eftersom dessa två kort har samma användar-ID, 12345, kan de inte båda tilldelas till arbetare.

## <a name="assign-extended-logon"></a>Tilldela förlängd inloggning

Som standard är endast chefer kan tilldela utökade inloggning till arbetstagarna. Tilldela utökad inloggning genom att navigera till **Utökad inloggning** i POS. Sök sedan efter en anställd genom att ange den anställdes operatörs-ID i sökfältet. Välj anställd och klicka sedan på **Tilldela**. På nästa sida, nallar eller skanna utökade inloggning tilldelas arbetaren. Om nallar eller skanna finnas framgångsrikt lydde, **OK-** knappen blir tillgänglig. Klicka på **OK för** att spara det utökade inloggning för arbetstagaren.

## <a name="delete-extended-logon"></a>Ta bort en utökad inloggning

Ta bort den utökade inloggning som är tilldelad till en arbetstagare, sökningen för arbetstagaren med **utökad logga på** . Välj anställd och klicka sedan på **Ta bort**. Alla utökade inloggningsbehörighet som associeras med att arbetstagaren är borttagen.

## <a name="use-extended-logon"></a>Med hjälp av utökade inloggning

När utökad inloggning är konfigurerad, och arbetstagaren har tilldelats en streckkod eller den magnetiska remsan, arbetaren bara nallar eller skanna hans eller hennes kort medan POS inloggningssidan visas. Om ett lösenord krävs också före inloggning kan fortsätta, arbetstagaren uppmanas du att ange sitt lösenord.

## <a name="extend-extended-logon"></a>Utvidga utökade inloggning

Om du inte vill använda den utökade inloggningsinformationen måste autentiseringsuppgifterna ha minst sex tecken och att de första fem tecknen (användar-ID:t) är unika. Det var ursprungligen avsett som ett exempel som utvecklare skulle kunna anpassa för att uppfylla kraven för en specifik implementering. (Det kan till exempel anpassas så att det stöder fler tecken eller använder olika säkerhetsverifieringsregler.) Detaljerad information om hur du bygger tillägg för utökad inloggning finns i [Utöka de utökade inloggningsfunktionerna för MPOS och Cloud POS](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/12/14/extending-the-extended-logon-functionality-for-mpos-and-cloud-pos/).

Inloggning tjänsten kan utökas för att stödja ytterligare utökade inloggning enheter, t.ex. palm scannrar. För mer information, se [POS extensibility dokumentation](dev-itpro/pos-extension/pos-extension-overview.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
