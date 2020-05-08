---
title: Definiera och underhåll butikskanaler
description: Det här avsnittet innehåller en översikt över processen för att ställa in tegelstens- och-murbruksbutiker, som kallas för butiker i Dynamics 365 Commerce. Här finns information om de uppgifter du måste utföra båda före och efter att du ställer in en butik.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0fbca2c9178cd372653287afdf72deaf75442604
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057924"
---
# <a name="define-and-maintain-retail-channels"></a>Definiera och underhålla butikskanaler

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller en översikt över processen för att ställa in tegelstens- och-murbruksbutiker, som kallas för butiker i Dynamics 365 Commerce. Här finns information om de uppgifter du måste utföra båda före och efter att du ställer in en butik.

Handel stöder flera kanaler, till exempel onlinebutiker, kundtjänst och fysiska butiker. En fysisk butik kallas för butik. Varje butik kan ha egna betalningsmetoder, prisgrupper, kassaregister (POS), intäkts- och utgiftskonton och personal. Du måste ställa in alla dessa element för en butik innan du skapar den. När du har skapat en butik tilldelar du produkter som du vill ha i butiken. Du tilldelar också medarbetare, register och kunder till butiken. Slutligen lägger du till den nya butiken i en organisationshierarki.

## <a name="setting-up-stores"></a>Ställa in butiker

Innan du kan ställa in en butik i Handel måste du utföra vissa obligatoriska uppgifter. Du kan sedan skapa butiken och lägga till information.

### <a name="prerequisites"></a>Förutsättningar

Du måste slutföra följande uppgifter innan du kan ställa in en butik:

1. Konfigurera organisationsstrukturen och ställ in organisationshierarkier för butikssortiment, lagerpåfyllnad och rapportering.
2. Ställ in ett lager som avser butiken.
3. Ställa in nummerserier för butiker, butiksutdrag och utdragverifikationer.
4. Konfigurera parametrar för Handel.
5. Ställa in betalningsmetoder som butiken godkänner.
6. Om du vill bearbeta kreditkortstransaktioner i kassorna kan du också ställa in betalningstjänster.
7. Ställa in momsgrupper.
8. Ställ in produkter. Som en del av den här uppgiften ställer du även in produkthierarkier, produktvarianter och produktsortiment.
9. Ställa in produktprisgrupper.
10. Ställ in produktprissättning. Som en del av den här uppgiften ställer du också in prisjusteringar, rabatter och rabattperioder.
11. Ställa in anställda.

    > [!NOTE]
    > Du måste också tilldela behörigheter till rätta arbetarna, så att de kan skriva in och utföra uppgifter genom att använda kassasystem.

12. Konfigurera kassaprofilerna som ska tilldelas till butiken. Den här uppgiften innefattar många uppgifter, till exempel ställa in kassor, offlineprofiler, kvittoformat och kvittoprofiler.

Granska alla uppgifter som ingår i förutsättningarna och slutför alla uppgifter som gäller för dig.

### <a name="set-up-a-store"></a>Ställ in en butik

När du har slutfört de obligatoriska uppgifterna slutför du dessa uppgifter för att ställa in detaljer för butiken:

1. Skapa en butik.
2. Tilldela en momsgrupp till butiken.
3. Tilldela accepterade betalningsmetoder till butiken.
4. Lägg till uppgifter i produktbeskrivningarna för de produkter som du erbjuder i din butik. Du kan till exempel lägga till oformaterad text och bilder. Dessa produktdetaljer visas i olika kontext, till exempel i kassaregistret eller på utskrivna etiketter.
5. Lägg till butiken till en standardorganisationshierarki som tilldelas för syftet **Butikssortiment**, **Butikspåfyllnad** eller **Butiksrapportering**.

### <a name="after-you-set-up-a-store"></a>När du har ställt in en butik

När du har angett information för butiken slutför du dessa uppgifter för att skicka den nya butiksinformationen till kassan.

1. Konfigurera kassaregister för butiken.
2. Tilldela produktsortiment i butiken.
3. Bearbeta sortiment för att generera listan med produkter som ingår i sortimentet och för att göra produkterna tillgängliga i butiken.
4. Skicka data, till exempel nummerserier, maskinvaruprofiler, kassaskärmlayouter till kassorna.
5. Publicera butiken för att skicka butikdata till kassan.
6. Kör jobben för att skicka butiksinformationen till kassan.

## <a name="organization-hierarchies"></a>Organisationshierarkier

Handel använder organisationshierarkier för att strukturera kanaler. Organisationshierarkier representerar relationerna mellan organisationer som utgör ett företag. När du ställer in butiker kan du lägga till dem till en organisationshierarki. Butikerna delar sedan data som används för sortiment, lagerpåfyllnad och rapportering.

> [!NOTE]
> Om du vill använda Commerce säljfunktioner, måste konfigurationsnyckeln **Flera leveransadresser** till aktiveras. Den här konfigurationsnyckeln finns i den konfigurationsnyckel för **handel** under **Systemadministration**\> **Konfiguration** \> **Licenskonfiguration**. Detta krävs på grund av olika valideringar baserat på leveransadressen som konfigurerats på försäljningsorderradnivå.
