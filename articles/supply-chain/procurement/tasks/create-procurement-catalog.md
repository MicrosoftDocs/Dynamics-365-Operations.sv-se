---
title: Skapa en anskaffningskatalog
description: Denna artikel förklarar hur du skapar en anskaffningskatalog.
author: GalynaFedorova
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8e35e8c5b5c93fa9aac914f04e7ea658748cb052
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869558"
---
# <a name="create-a-procurement-catalog"></a>Skapa en anskaffningskatalog

[!include [banner](../../includes/banner.md)]

Denna artikel förklarar hur du skapar en anskaffningskatalog. Den här uppgiften utförs vanligtvis av ett anskaffningsproffs. Du kan också lära dig om hur medarbetare kan använda katalogen när de skapar en rekvisition. Innan du kan skapa en katalog måste det finnas en anskaffningskategorihierarki i systemet. Hierarkin ärvs från den nya katalogen, tillsammans med alla produkter som finns i hierarkin. Du kan använda den här handboken i demonstrationdataföretaget USMF, där anskaffningskategorihierarkin är tillgänglig, samt i exemplen som används i procedurstegen.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Se till att en anskaffningskategorihierarki finns
1. Gå till **Navigeringsfönstret > Moduler > Anskaffning och källa > Anskaffningskategorier**. En anskaffningskategorihierarki är tillgänglig i demoföretaget USMF och produkter har lagts till i kategorin **kontorsmaskiner/datorer**. Om du kör den här proceduren som en uppgiftsguide måste du låsa upp guiden om du vill bläddra genom kategorin. Om en hierarki inte är tillgänglig kan du skapa den genom att klicka på **Ny**. Detta kan bara göras en gång.  
2. Stäng sidan.

## <a name="create-a-catalog"></a>Skapa en katalog
1. Gå till **Navigeringsfönstret > Moduler > Anskaffning och källa > Kataloger >Anskaffningskataloger**.
2. Välj **Ny anskaffningskatalog** om du vill öppna dialogrutan.
3. Skriv ett värde i fältet **Namn**.
4. Välj **OK**.
5. Expandera **ANSKAFFNINGSKATEGORIER FÖR FÖRETAG** i trädet.
6. Expandera **KONTORSMASKINER** i trädet.
7. Välj **Datorer** i trädet.

  - Produkterna från anskaffningkategorin visas i listan. Om du vill lägga till en produkt till en kategori måste du göra detta på sidan **Anskaffningskategorihierarki** eller på sidan **Artikeldetaljer**.  
  - **Standard**-uppdateringstypen bestämmer om nya produkter som har lagts till i anskaffningskategorihierarkin omedelbart är synliga i katalogen. Om uppdateringstypen är inställd på **Dynamisk** kommer ändringar att synas på en gång. Om uppdateringstypen är **Statisk** är nya produkter endast synliga för personer som använder katalogen efter att katalogen har publicerats igen. Åtgärden **Publicera** är tillgänglig i åtgärdsfönstret överst på sidan. Om produkter tas bort från anskaffningskategorihierarkin är ändringen omedelbart synlig oavsett värdet i fältet **Standard**-uppdateringtyp.  

8. I åtgärdsfönstret, välj **kategorinavigering** och se till att **aktivera** är markerad.
9. Välj **Aktivera katalog**.
10. Stäng sidan.

## <a name="make-the-catalog-visible"></a>Gör katalogen synlig
1. Gå till **navigeringsfönster > moduler > anskaffning och källa > inställningar > principer > inköpspolicyer**.
2. Välj **anskaffningspolicy USMF**. Du måste välja inköpspolicyn för den juridiska person som arbetaren kopplade till din användarprofil, som tillåter att bekonfigurera produkter. I USMF-demonstrationdatan är användaren Admin kopplad till arbetaren som kallas **Julia Funderburk**, och hon beställer produkter i USMF som standard.  
3. Välj katalogen som du nyss skapat.
4. Välj **OK**.

## <a name="use-the-catalog"></a>Använd katalogen
1. Gå till **Navigeringsfönster > Moduler > Anskaffning och källa > Inköpsrekvisitioner > Alla inköpsrekvisitioner**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **Namn**.
4. Välj **OK**.
5. Välj **Lägg till produkter**.
6. Hitta och markera önskad post i listan. Du kan använda kategorihierarkin till vänster eller filtret högst upp i listan om du vill filtrera.  
7. Välj **Lägg till på rader**.
8. Välj **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]