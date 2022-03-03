---
title: Undersöka eller lösa undantag
description: Leverantörsfakturapolicyer körs när du bokför en leverantörsfaktur genom att använda leverantörsfakturasidan, och när du öppnar sidan för brott mot leverantörsfakturapolicyn.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32ff53198f61e1d1af3c437e9488c2a246cf820a
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2022
ms.locfileid: "8110029"
---
# <a name="research-or-resolve-exceptions"></a>Undersöka eller lösa undantag

[!include [banner](../../includes/banner.md)]

Leverantörsfakturapolicyer körs när du bokför en leverantörsfaktura genom att använda sidan **leverantörsfaktura** sida och när du öppnar leverantörsfakturasidan **Regelöverträdelser**. Du kan även konfigurera leverantörsfakturaarbetsflödet om du vill köra leverantörsfakturapolicyer varje gång som du skickar in en faktura till arbetsflödet. 

Leverantörsfakturapolicyer gäller inte för fakturor som har skapats i **Fakturaregister** eller **fakturajournalen**. 

Fakturamatchningsvalidering använder inte leverantörsfakturapolicyer, utan ställs in på sidan med **leverantörsreskontraparametrar**.

I den här registreringen används demonstrationsföretaget USMF. Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan. Innan du börjar kontrollerar du att **konfigurationsnyckeln för fakturamatchning** har valts.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Förbered för att skapa leverantörsfakturapolicyer
1. Gå till **Leverantörsreskontra > Inställningar > Parametrar för leverantörsreskontra.**
2. Klicka på fliken **Fakturavalidering**.
3. Markera eller avmarkera kryssrutan **Uppdatera status för fakturahuvud automatiskt**.
4. Klicka på **OK**.
5. Välj ett alternativ i fältet **Bokför faktura med avvikelser**.
6. Stäng sidan.
7. Gå till **Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer**.
8. Klicka på **Parametrar**.
9. Klicka på **Lägg till**.
10. Stäng sidan.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Skapa policyregeltyper för leverantörsfakturor
1. Gå till **Leverantörsreskontra > Policyinställningar > Policyregeltyper för leverantörsfaktura**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Regelnamn**.
4. I fältet **Beskrivning** anger du ett värde.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Frågenamn**.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Klicka på **Spara**.
9. Stäng sidan.

## <a name="define-a-vendor-invoice-policy"></a>Definiera en leverantörsfakturapolicy
1. Gå till **Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Namn**.
4. I fältet **Beskrivning** anger du ett värde.
5. Expandera eller komprimera avsnittet **Policyorganisationer**.
6. Välj det ”Contoso Entertainment System USA" i trädet..
7. Klicka på **Lägg till**.
8. Expandera eller komprimera avsnittet **Policyregler**.
9. Klicka på **Skapa regel för policyn.**
10. Skriv ett värde i fältet **Beskrivning av policyregel**.
11. Klicka på **Filter**.
12. Klicka på **Lägg till**.
13. Markera vald rad i listan.
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Register**.
15. Klicka på länken på den valda raden i listan.
16. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Härlett register**.
17. Klicka på länken på den valda raden i listan.
18. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Fält**.
19. Ange ett värde i fältet **Fält**.
20. Stäng sidan.
21. I fältet **Kriterier** skriver du ett värde.
22. Klicka på **OK**.
23. Klicka på **OK**.
24. Stäng sidan.
25. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
