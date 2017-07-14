---
title: "Konfigurera utökad inloggning för Cloud POS och MPOS"
description: "Detta avsnitt täcker dina alternativ för att ställa in utökad inloggning för molnbaserad kassa och Retail Modern POS (MPOS)."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 0b7e5ed451497aea1c2ce798af2b717705538d47
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017



---

# Konfigurera utökad inloggning för Cloud POS och MPOS
<a id="set-up-extended-logon-functionality-for-cloud-pos-and-mpos" class="xliff"></a>

[!include[banner](includes/banner.md)]


Detta avsnitt täcker dina alternativ för att ställa in utökad inloggning för molnbaserad kassa och Retail Modern POS (MPOS).

Ställa in utökade inloggning
<a id="setting-up-extended-logon" class="xliff"></a>
=========================

Du hittar inställningarna för streckkodsmasker på **Butik** &gt; **Kanalinställning** &gt; **Kassainställning** &gt; **Kassaprofiler** &gt; **Funktionsprofiler**. **Funktionerna** snabbfliken innehåller följande alternativ som är relaterade till utökad inloggning.

### Streckkodsinloggning för personal
<a id="staff-bar-code-logon" class="xliff"></a>

När **personalen bar kod inloggning** är aktiverad, arbetstagare som har en utökad inloggning tilldelas deras försäljningsställe (POS) inloggningsuppgifter kan logga in med hjälp av en streckkod.

### Streckkodsinloggning för personal kräver lösenord
<a id="staff-bar-code-logon-requires-password" class="xliff"></a>

När **personalen bar kod inloggning kräver lösenord** alternativ är aktiverat personal bar kod inloggning väljer endast de arbetstagare som har tilldelats utökade inloggning att presenteras. Arbetstagare måste ange sitt lösenord när det här alternativet är aktiverat.

### Personalkortsinloggning
<a id="staff-card-logon" class="xliff"></a>

När **personalen kort inloggning** är aktiverad, arbetstagare som har en utökad inloggning tilldelas sina POS inloggningsuppgifter kan logga in med en magnetremsa.

### Personalkortsinloggning kräver lösenord
<a id="staff-card-logon-requires-password" class="xliff"></a>

När **personalen kort inloggning kräver lösenord** alternativ är aktiverat personal kort inloggning väljer endast de arbetstagare som har tilldelats utökade inloggning att presenteras. Arbetstagare måste ange sitt lösenord när det här alternativet är aktiverat.

Tilldela en utökad inloggning
<a id="assigning-an-extended-logon" class="xliff"></a>
===========================

Som standard är endast chefer kan tilldela utökade inloggning till arbetstagarna. Tilldela utökad inloggning genom att navigera till **Utökad inloggning** i kassan. Sök sedan efter en anställd genom att ange hans eller hennes operatörs-ID i sökfältet. Välj anställd och klicka sedan på **Tilldela**. På nästa sida, nallar eller skanna utökade inloggning tilldelas arbetaren. Om nallar eller skanna finnas framgångsrikt lydde, **OK-** knappen blir tillgänglig. Klicka på **OK för** att spara det utökade inloggning för arbetstagaren.

Ta bort en utökad inloggning
<a id="deleting-an-extended-logon" class="xliff"></a>
==========================

Ta bort den utökade inloggning som är tilldelad till en arbetstagare, sökningen för arbetstagaren med **utökad logga på** . Välj anställd och klicka sedan på **Ta bort**. Alla utökade inloggningsbehörighet som associeras med att arbetstagaren är borttagen.

Utvidga utökade inloggning
<a id="extending-extended-logon" class="xliff"></a>
========================

Inloggning tjänsten kan utökas för att stödja ytterligare utökade inloggning enheter, t.ex. palm scannrar. För mer information, se POS extensibility dokumentation.

Med hjälp av utökade inloggning
<a id="using-extended-logon" class="xliff"></a>
====================

När utökad inloggning är konfigurerad, och arbetstagaren har tilldelats en streckkod eller den magnetiska stripen, arbetaren bara nallar eller skanna hans eller hennes kort medan POS inloggningssidan visas. Om ett lösenord krävs också före inloggning kan fortsätta, arbetstagaren uppmanas du att ange sitt lösenord.




