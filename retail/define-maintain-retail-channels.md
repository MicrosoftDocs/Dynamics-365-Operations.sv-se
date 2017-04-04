---
title: "Definiera och underhåll butikskanaler"
description: "Den här artikeln innehåller en översikt över processen när du ställer in bankkontor och andra butiker som benämns butiker i Microsoft Dynamics 365 för operationer. Här finns information om de uppgifter du måste utföra båda före och efter att du ställer in en butik."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: b775ba34ef7d88dd0b47904e4a3e9be79664f14b
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-maintain-retail-channels"></a>Definiera och underhåll butikskanaler

Den här artikeln innehåller en översikt över processen när du ställer in bankkontor och andra butiker som benämns butiker i Microsoft Dynamics 365 för operationer. Här finns information om de uppgifter du måste utföra båda före och efter att du ställer in en butik.

Butik och handel i Dynamics 365 för operationer stöder flera återförsäljare, till exempel onlinebutiker, kundtjänst och bankkontor och andra butiker. I Butik och handel kallas en fysisk butik för butik. Varje butik kan ha egna betalningsmetoder, prisgrupper, kassaregister (POS), intäkts- och utgiftskonton och personal. Du måste ställa in alla dessa element för en butik innan du skapar den. När du har skapat en butik tilldelar du produkter som du vill ha i butiken. Du tilldelar också medarbetare, register och kunder till butiken. Slutligen lägger du till den nya butiken i en organisationshierarki.

## <a name="setting-up-retail-stores"></a>Ställa in butiker
Innan du kan skapa en butik i Dynamics 365 för åtgärder måste du utföra vissa nödvändiga uppgifter. Du kan sedan skapa butiken och lägga till information.

### <a name="prerequisites"></a>Krav

Du måste slutföra följande uppgifter innan du kan ställa in en butik:

1.  Konfigurera organisationsstrukturen och ställ in organisationshierarkier för butikssortiment, lagerpåfyllnad och rapportering.
2.  Ställ in ett lager som avser butiken.
3.  Ställa in nummerserier för butiker, butiksutdrag och utdragverifikationer.
4.  Konfigurera parametrar för Detaljhandel.
5.  Ställa in betalningsmetoder som butiken godkänner.
6.  Om du vill bearbeta kreditkortstransaktioner i butikskassorna kan du också ställa in betalningstjänster.
7.  Ställa in momsgrupper.
8.  Ställ in butiksprodukter. Som en del av den här uppgiften ställer du även in butiksprodukthierarkier, produktvarianter och produktsortiment.
9.  Ställa in produktprisgrupper.
10. Ställa in butiksproduktprissättning. Som en del av den här uppgiften ställer du också in prisjusteringar, rabatter och rabattperioder.
11. Ställa in anställda. **Anmärkning:** måste du också tilldela behörighet arbetstagare, så att de kan logga in och utföra åtgärder med hjälp av Dynamics 365 för operationer i Retail POS-system.
12. Konfigurera Retail POS-profilerna som ska tilldelas till butiken. Den här uppgiften innefattar många uppgifter, till exempel ställa in kassor, offlineprofiler, kvittoformat och kvittoprofiler.

Granska alla uppgifter som ingår i förutsättningarna och slutför alla uppgifter som gäller för dig.

### <a name="set-up-a-retail-store"></a>Skapa en butik

När du har slutfört de obligatoriska uppgifterna slutför du dessa uppgifter för att ställa in detaljer för butiken:

1.  Skapa en butik.
2.  Tilldela en momsgrupp till butiken.
3.  Tilldela accepterade betalningsmetoder till butiken.
4.  Lägg till uppgifter i produktbeskrivningarna för de produkter som du erbjuder i din butik. Du kan till exempel lägga till oformaterad text och bilder. Dessa produktdetaljer visas i olika kontext, till exempel i kassaregistret eller på utskrivna etiketter.
5.  Lägg till butiken till en standardorganisationshierarki som tilldelas för syftet **Butikssortiment**, **Butikspåfyllnad** eller **Butiksrapportering**.

### <a name="after-you-set-up-a-retail-store"></a>När du har ställt in en butik

När du har angett information för butiken slutför du dessa uppgifter för att skicka den nya butiksinformationen till Retail POS.

1.  Konfigurera kassaregister för butiken.
2.  Tilldela produktsortiment i butiken.
3.  Bearbeta sortiment för att generera listan med produkter som ingår i sortimentet och för att göra produkterna tillgängliga i butiken.
4.  Skicka data, till exempel nummerserier, maskinvaruprofiler, kassaskärmlayouter till Retail POS-kassorna.
5.  Publicera butiken för att skicka butiksdata till Retail POS.
6.  Kör jobben för att skicka butiksinformationen till Retail POS.

## <a name="organization-hierarchies"></a>Organisationshierarkier
Retail använder organisationshierarkier i Microsoft Dynamics AX för att strukturera butikskanaler. Organisationshierarkier representerar relationerna mellan organisationer som utgör ett företag. När du ställer in butiker kan du lägga till dem till en organisationshierarki. Butikerna delar sedan data som används för sortiment, lagerpåfyllnad och rapportering.


