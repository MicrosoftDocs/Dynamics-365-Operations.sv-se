---
title: Parametrar för konstruktionsändringshantering
description: Det här avsnittet förklarar hur du konfigurerar funktioner för hantering av tekniska förändringar för Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 106c3a79236bcb8112ecbd48e29f3f5f3148a867
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7581018"
---
# <a name="engineering-change-management-parameters"></a>Parametrar för konstruktionsändringshantering

[!include [banner](../includes/banner.md)]

Sidan **Parametrar för konstruktionsändringshantering** innehåller inställningsparametrar som ändrar standardbeteendet som är relaterat till frisläppning av produktstrukturen och processer för konstruktionsändringshantering.

## <a name="open-the-engineering-change-management-parameters-page"></a>Öppna sidan Parametrar för konstruktionsändringshantering

Om du vill öppna sidan **Parametrar för konstruktionsändringshantering** gå till **Konstruktionsändringshantering \> Inställningar \> Parametrar för konstruktionsändringshantering**. Du kan sedan ange fälten enligt beskrivningen i de återstående avsnitten i det här avsnittet.

## <a name="release-control-tab"></a>Fliken frisläppningskontroll

I följande tabell beskrivs fälten som är tillgängliga på fliken **Frisläppningskontroll** i **Parametrar för konstruktionsändringshantering**. Dessa fält påverkar produktstrukturprocessen för frisläppning.

| Fält | beskrivning |
|---|---|
| Regel för artikelnummer | Välj hur artikelnumret ska definieras när produkten frisläpps till en juridisk person. Välj *Tekniskt produktnummer* om produktnumret i den mottagande juridiska enheten ska matcha produktnumret i det tekniska företaget. Välj *Lokal artikelnummerserie* om produkten ska ta nästa nummer i nummerserien för produktnummer i mottagande juridiska person. |
| Regel för strukturlistenamn | Välj hur namnet på strukturlistan definieras när produkten tas emot (frisläppta) i en juridisk person. Välj antingen *ingenjörsnamn* eller *Artikelnummer för inleverans*. |
| Regel för flödesnamn | Välj hur ruttnamnet ska definieras när en produkts rutt tas emot (frisläpps) i en juridisk enhet. Välj antingen *ingenjörsnamn* eller *Artikelnummer för inleverans*. |
| Kör strukturlistekontroll | Välj om en strukturlistekontroll ska köras när produkten är inlevererad (frisläppt) i en juridisk person. |
| Frisläpp beteende för inaktiv strukturlista | Välj om en produkt kan frisläppas om den har en inaktiv strukturlista. Välj *Acceptera*, *Endast varning* eller *Inte tillåtet*. |
| Frisläppningsbeteende för inaktivt flöde | Välj om en produkt kan frisläppas om den har en inaktiv rutt. Välj *Acceptera*, *Endast varning* eller *Inte tillåtet*.|
| Produktgodkännande | Välj om ett ytterligare steg för godkännande krävs innan produkten kan frisläppas i den juridiska personen. Välj *manuell* om du vill lägga till godkännandesteget. I det här fallet visar sidan **Öppna produktversioner** visar produkterna. Välj *automatisk* om du vill att produkten ska visas direkt på sidan **frisläppta produkter** i den juridiska målpersonen omedelbart efter att produkten frisläppts tillsammans med dess frisläppningsproduktstruktur. |

## <a name="engineering-change-management-tab"></a>Fliken Konstruktionsändringshantering

I följande tabell beskrivs fälten som är tillgängliga på fliken **Konstruktionsändringshantering** i **Parametrar för konstruktionsändringshantering**. Dessa inställningar påverkar processerna för konstruktionsändringshantering.

| Fält | beskrivning |
|---|---|
| Kategori | Den standardkategori som ska användas när en begäran om konstruktionsändring skapas. |
| Prioritet | Den standardprioritet som ska användas när en begäran om konstruktionsändring skapas. |
| Allvarlighetsregel | Välj hur allvarlighetsgraden för en teknisk ändringsorder ska fastställas. Välj *manuell* om användaren förväntas ange ett värde i fältet **allvarlighetsgrad**. Välj *Beräkna* om du vill att systemet beräknar värdet av fältet **Allvarlighetsgrad** när du väljer **Beräkna allvarlighetsgrad** i åtgärdsfönstret för teknisk ändringsorder. I det här fallet använder systemet allvarlighetsreglerna som definieras på sidan **Allvarlighetsregel**. Välj *Beräkna automatiskt* om du vill att värdet i fältet **Allvarlighetsgrad** beräknas automatiskt och fyllas i enligt regeluppsättningarna för allvarlighetsgrad. |
| Återutge påverkade produkter | Det här fältet används när du återlanserar produkter via en teknisk ändringsorder. Du kan välja om alla produkter eller endast de berörda produkterna ska föreslås i dialogrutan **Versioner**. |
| Strukturlistenivåer att frisläppa | Djupet på strukturnivån som ska frisläppas. Om strukturlistan har fler nivåer (dvs. om den är djupare) än värdet som anges här frigörs bara nivåerna upp genom det angivna värdet. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]