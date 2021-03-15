---
title: Undersöka eller lösa undantag
description: Leverantörsfakturapolicyer körs när du bokför en leverantörsfaktur genom att använda leverantörsfakturasidan, och när du öppnar sidan för brott mot leverantörsfakturapolicyn.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 727676d060b77633d4ff4f31dabbd7825ca19aca
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971788"
---
# <a name="research-or-resolve-exceptions"></a>Undersöka eller lösa undantag

[!include [banner](../../includes/banner.md)]

Leverantörsfakturapolicyer körs när du bokför en leverantörsfaktur genom att använda leverantörsfakturasidan, och när du öppnar sidan för brott mot leverantörsfakturapolicyn. Du kan även konfigurera leverantörsfakturaarbetsflödet om du vill köra leverantörsfakturapolicyer varje gång som du skickar in en faktura till arbetsflödet. 

Leverantörsfakturapolicyer gäller inte för fakturor som har skapats i ankomstregistreringen eller fakturajournalen. 

Fakturamatchningsvalidering använder inte leverantörsfakturapolicyer, utan ställs in på sidan med leverantörsreskontraparametrar.

I den här registreringen används demonstrationsföretaget USMF. Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan. Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Förbered för att skapa leverantörsfakturapolicyer
1. Gå till Leverantörsreskontra > Inställningar > Parametrar för leverantörsreskontra.
2. Klicka på fliken Fakturavalidering.
3. Markera eller avmarkera kryssrutan Uppdatera status för fakturahuvud automatiskt.
4. Klicka på OK.
5. Välj ett alternativ i fältet Bokför faktura med avvikelser.
6. Stäng sidan.
7. Gå till Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer.
8. Klicka på Parametrar.
9. Klicka på btnAdd.
10. Stäng sidan.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Skapa policyregeltyper för leverantörsfakturor
1. Gå till Leverantörsreskontra > Policyinställningar > Policyregeltyper för leverantörsfaktura.
2. Klicka på Ny.
3. I fältet Regelnamn, skriv ett värde.
4. Ange ett värde i fältet Beskrivning.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Frågenamn.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Klicka på Spara.
9. Stäng sidan.

## <a name="define-a-vendor-invoice-policy"></a>Definiera en leverantörsfakturapolicy
1. Gå till Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange ett värde i fältet Beskrivning.
5. Expandera eller komprimera avsnittet Policyorganisationer.
6. Välj det ”Contoso Entertainment System USA" i trädet..
7. Klicka på Lägg till.
8. Expandera eller komprimera avsnittet Policyregler.
9. Klicka på Skapa policyregel.
10. I fältet Policyregel, skriv ett värde.
11. Klicka på Filter.
12. Klicka på Lägg till.
13. Markera vald rad i listan.
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Register.
15. Klicka på länken på den valda raden i listan.
16. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Härlett register.
17. Klicka på länken på den valda raden i listan.
18. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Fält.
19. Ange ett värde i fältet Fält.
20. Stäng sidan.
21. Ange ett värde i fältet Kriterier.
22. Klicka på OK.
23. Klicka på OK.
24. Stäng sidan.
25. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]