---
title: Ställ in leverantörsfakturapolicyer
description: Det här avsnittet innehåller information om hur du ställer in leverantörsfakturapolicyer.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72f017294c976dcd1b7ddda01ac9e39252f036d6
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250289"
---
# <a name="set-up-vendor-invoice-policies"></a>Ställ in leverantörsfakturapolicyer

[!include [task guide banner](../../includes/task-guide-banner.md)]

Det här avsnittet innehåller information om hur du ställer in leverantörsfakturapolicyer. Leverantörsfakturapolicyer körs när du bokför en leverantörsfaktur genom att använda leverantörsfakturasidan, och när du öppnar sidan för brott mot leverantörsfakturapolicyn. Du kan även konfigurera leverantörsfakturaarbetsflödet om du vill köra leverantörsfakturapolicyer varje gång som du skickar in en faktura till arbetsflödet. 

- Leverantörsfakturapolicyer gäller inte för fakturor som har skapats i ankomstregistreringen eller fakturajournalen.  
- Fakturamatchningsvalidering använder inte leverantörsfakturapolicyer, utan ställs in på sidan med leverantörsreskontraparametrar.  
- I den här registreringen används demonstrationsföretaget USMF. Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan. Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Förbered för att skapa leverantörsfakturapolicyer
1. Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Inställningar > Parametrar för leverantörsreskontra**.
2. Välj fliken **Fakturavalidering**
3. Markera eller avmarkera kryssrutan **Uppdatera status för fakturahuvud automatiskt**.
4. Välj **OK**.
5. Välj ett alternativ i fältet **Bokför faktura med avvikelser**.
6. Stäng sidan.
7. Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer**.
8. Välj **parametrar**.
9. Markera **Lägg till**.
10. Stäng sidan om du vill gå tillbaka till startsidan.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Skapa policyregeltyper för leverantörsfakturor
1. Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Policyinställningar > Policyregeltyper för leverantörsfaktura**.
2. Välj **Ny**.
3. Ange värden i fälten **Regelnamn** och **Beskrivning**.
4. I fältet **frågenamn** väljer du den nedrullningsbara knappen för att öppna sökningen och väljer sedan önskad post.
5. Välj **Spara**.
6. Stäng sidan om du vill gå tillbaka till startsidan.

## <a name="define-a-vendor-invoice-policy"></a>Definiera en leverantörsfakturapolicy
1. Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer**.
2. Välj **Ny**.
3. Ange värden i fälten **Namn** och **Beskrivning**.
4. Expandera eller komprimera avsnittet **Policyorganisationer**.
5. I trädet, välj **Contoso Entertainment System USA**.
6. Markera **Lägg till**.
7. Expandera eller komprimera avsnittet **Policyregler**.
8. Välj **Skapa policyregel**.
9. Skriv ett värde i fältet **Beskrivning av policyregel**.
10. Välj **filter**.
11. Markera **Lägg till**. Välj önskad post.
12. I fälten **Tabell**, **Härlett register** och **Fält** väljer du eller anger alternativ från listrutemenyer.
13. Stäng sidan.
14. I fältet **Kriterier** skriver du ett värde.
15. Välj **OK**.
16. Välj **OK**.
17. Stäng sidorna om du vill gå tillbaka till startsidan.

