---
title: Definiera granskningspolicyer för källdokument
description: I det här avsnittet visar vi hur du ställer in och kör granskningspolicyregler.
author: panolte
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 62ebe3d6ba1208bd5f9a2082969b1960c413c152
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836971"
---
# <a name="define-audit-policies-for-source-documents"></a>Definiera granskningspolicyer för källdokument

[!include [banner](../../includes/banner.md)]

I det här avsnittet visar vi hur du ställer in och kör granskningspolicyregler. I exemplet används utgiftsrapporter av typen hotellutgift. I den här proceduren används demonstrationsföretaget USMF. Revisorrollen har rätt behörighet för att utföra dessa uppgifter.

1. I navigeringsfönstret går du till **Moduler > Revision > Inställningar > Policyregeltyp**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **Regelnamn**.
4. I fältet **Beskrivning** anger du ett värde.
5. I fältet **Frågenamn** väljer du **Utgiftsrapportrad**
6. I fältet **Frågetyp** väljer du **Sammansättning**
7. I fältet **Juridiskt person** väljer du **Juridisk person**
8. I fältet **Dokumentdatumreferens** väljer du **Datum och tid för ändring**
9. Välj **Spara**.
10. I navigeringsfönstret går du till **Moduler > Revision > Inställningar > Granskningspolicyer**.
11. Välj **Ny**.
12. Skriv ett värde i fältet **Namn**.
13. Expandera avsnittet **Policyorganisationer**.
14. Välj **Contoso Entertainment System USA** i trädet och välj **Lägg till**.
15. Välj **Contoso Consulting USA** i trädet och välj **Lägg till**.
16. Välj **Contoso Retail USA** i trädet och välj **Lägg till**.
17. Komprimera avsnittet **Policyorganisationer**.
18. Expandera avsnittet **Policyregler**.
19. I listan söker du efter och väljer den policyregel som tidigare har skapats.
20. Välj **Skapa policyregel**.
21. I fältet **Gäller från** anger du datum och tid.
22. Välj **filter**.
23. Välj raden för **Utgiftskategori** i listan och ställ in detaljerna till **Hotell**.
24. I fältet **Kriterier** anger du eller väljer ett värde.
25. Välj fliken **Sammansättning**.
26. Markera **Lägg till**.
27. Välj fältvärdet **Transaktionsbelopp** i listan.
28. Ange eller välj ett värde i fältet **Fält**.
29. I fältet **AggregateFunction** väljer du **Sum**.
30. Välj fliken **Gruppera efter**.
31. Markera **Lägg till**.
32. Välj värdet **Medarbetare** i listan.
33. Markera **Lägg till**.
34. Välj värdet **Utgiftskategori** i listan.
35. Ange eller välj ett värde i fältet **Fält**.
36. Välj fliken **Har**.
37. Markera **Lägg till**.
38. Välj **Transaktionsbelopp**.
39. Ange eller välj ett värde i fältet **Fält**.
40. I fältet **AggregateFunction** väljer du **Sum**.
41. I fältet **Kriterier** skriver du `>2000`.
42. Välj **OK**.
43. Välj **Test**.
44. I fältet **Startdatum för dokumenturval**, ange datum och tid.
45. I fältet **Slutdatum för dokumenturval**, ange datum och tid.
46. Välj **Kör test**.
47. I åtgärdsfönstret, välj **Granskningspolicy**.
48. Välj **Ytterligare alternativ**.
49. I fältet **Startdatum**, ange datum och tid.
50. I fältet **Slutdatum**, ange datum och tid.
51. Välj **Batch**.
52. Expandera avsnittet **Kör i bakgrunden**.
53. Välj **Ja** i fältet **Batchbearbetning**.
54. Välj **OK**.
55. I navigeringsfönstret går du till **Moduler > Revision > Granskningsärenden**.
56. Hitta och markera önskad post i listan.
57. Expandera avsnittet **Associationer**.
58. Hitta och markera önskad post i listan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]