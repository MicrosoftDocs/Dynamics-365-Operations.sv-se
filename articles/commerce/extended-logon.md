---
title: Konfigurera utökad inloggning för MPOS och molnkassor
description: Detta avsnitt täcker dina alternativ för att ställa in utökad inloggning för molnbaserad kassa och Retail Modern POS (MPOS).
author: rubencdelgado
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f9d8889581e2e11fa5261805c866a6014df57611
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027586"
---
# <a name="set-up-extended-logon-functionality-for-mpos-and-cloud-pos"></a>Ställa in utökad inloggningsfunktion för MPOS och molnbaserad kassa

[!include [banner](includes/banner.md)]

Detta avsnitt täcker dina alternativ för att ställa in utökad inloggning för molnbaserad kassa och Retail Modern POS (MPOS).

## <a name="setting-up-extended-logon"></a>Ställa in utökade inloggning

Du hittar inställningarna för streckkod masker på **Butik och handel** &gt; **kanalinställning** &gt; **kassainställning** &gt; **kassaprofiler** &gt; **funktionsprofiler**. **Funktionerna** snabbfliken innehåller följande alternativ som är relaterade till utökad inloggning.

### <a name="staff-bar-code-logon"></a>Streckkodsinloggning för personal

När **personalen bar kod inloggning** är aktiverad, arbetstagare som har en utökad inloggning tilldelas deras försäljningsställe (POS) inloggningsuppgifter kan logga in med hjälp av en streckkod.

### <a name="staff-bar-code-logon-requires-password"></a>Streckkodsinloggning för personal kräver lösenord

När **personalen bar kod inloggning kräver lösenord** alternativ är aktiverat personal bar kod inloggning väljer endast de arbetstagare som har tilldelats utökade inloggning att presenteras. Arbetstagare måste ange sitt lösenord när det här alternativet är aktiverat.

### <a name="staff-card-logon"></a>Personalkortsinloggning

När **personalen kort inloggning** är aktiverad, arbetstagare som har en utökad inloggning tilldelas sina POS inloggningsuppgifter kan logga in med en magnetremsa.

### <a name="staff-card-logon-requires-password"></a>Personalkortsinloggning kräver lösenord

När **personalen kort inloggning kräver lösenord** alternativ är aktiverat personal kort inloggning väljer endast de arbetstagare som har tilldelats utökade inloggning att presenteras. Arbetstagare måste ange sitt lösenord när det här alternativet är aktiverat.

## <a name="assigning-an-extended-logon"></a>Tilldela en utökad inloggning

Som standard är endast chefer kan tilldela utökade inloggning till arbetstagarna. Tilldela utökad inloggning genom att navigera till **Utökad inloggning** i POS. Sök sedan efter en anställd genom att ange den anställdes operatörs-ID i sökfältet. Välj anställd och klicka sedan på **Tilldela**. På nästa sida, nallar eller skanna utökade inloggning tilldelas arbetaren. Om nallar eller skanna finnas framgångsrikt lydde, **OK-** knappen blir tillgänglig. Klicka på **OK för** att spara det utökade inloggning för arbetstagaren.

## <a name="deleting-an-extended-logon"></a>Ta bort en utökad inloggning

Ta bort den utökade inloggning som är tilldelad till en arbetstagare, sökningen för arbetstagaren med **utökad logga på** . Välj anställd och klicka sedan på **Ta bort**. Alla utökade inloggningsbehörighet som associeras med att arbetstagaren är borttagen.

## <a name="extending-extended-logon"></a>Utvidga utökade inloggning

Inloggning tjänsten kan utökas för att stödja ytterligare utökade inloggning enheter, t.ex. palm scannrar. För mer information, se POS extensibility dokumentation.

## <a name="using-extended-logon"></a>Med hjälp av utökade inloggning

När utökad inloggning är konfigurerad, och arbetstagaren har tilldelats en streckkod eller magnetremsa, behöver arbetstagaren bara dra eller skanna sitt kort medan POS-inloggningssidan visas. Om ett lösenord krävs före inloggning kan fortsätta, uppmanas arbetstagaren att ange sitt lösenord.


[!INCLUDE[footer-include](../includes/footer-banner.md)]