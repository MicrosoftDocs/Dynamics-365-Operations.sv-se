---
title: Anställningverifiering av i9-verifiering
description: Immigration Reform and Control Act kräver att amerikanska arbetsgivare verifierar nyanställdas anställningskvalifikationer.
author: ShielaSogge
ms.date: 01/10/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, HcmPersonIdentificationNumber, Hcmi9Document
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b76102111a8506882f2301d76856ae1a34a7c704
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065691"
---
# <a name="employment-verification-i9-verification"></a>Anställningverifiering av i9-verifiering

[!include [banner](../../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../../includes/peap-1.md)]

Immigration Reform and Control Act kräver att amerikanska arbetsgivare verifierar nyanställdas anställningskvalifikationer. I den här proceduren går du igenom stegen för att registrera nödvändiga dokument för verifiering av I-9. Använd företaget USMF för den här proceduren.

1. Gå till **Personal \> Arbetare \> Medarbetare**.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel med värdet **Vince** för fältet **Namn**.
3. Välj medarbetare. Välj till exempel **Vince Prado**. 
4. Välj snabbfliken **Personuppgifter**.
5. Välj **Identifieringsnummer**.
6. Välj **Ny**.
7. Välj den identifieringstyp som du registrerar. Välj till exempel **Pass**.
8. I fältet **Antal**, skriv ett värde.
9. I fältet **Primär**, välj **Ja**.
10. Ange en kort beskrivning av identifieringsposten i fältet **Beskrivning**.
11. I fältet **utfärdande organet** väljer du det organ som har utfärdat identifieringsformuläret för arbetaren. Välj till exempel **Myndighet**.
12. Ange det datum då det utfärdande organet har utfärdat identifieringsformuläret för arbetaren. Ange till exempel **02/15/2011** (15 februari 2011).
13. Ange det datum då identifieringsformuläret upphör att gälla. Ange till exempel **2/15/2021** (15 februari 2021).
14. Välj **Spara**.
15. Stäng sidan.
16. Välj fliken **Anställning**.
17. Välj **I-9**.
18. Välj **Ny**.
19. Välj ett alternativ i fältet **Kvalifikation**.

    Om medarbetaren inte är amerikansk medborgare måste du ange arbetarens inresenummer eller nummer för utländska medborgare med uppehållstillstånd.

20. Välj alternativet **GroupListA**.

    Vilken lista du väljer är beroende av vilken form av identifiering som arbetaren har angett. En arbetare måste tillhandahålla antingen ett dokument från Lista A eller ett dokument från både Lista B och Lista C. Om arbetaren till exempel har ett pass kan du välja Lista A. Om arbetaren bara har ett körkort och ett personkort måste du dock välja Lista B och Lista C.

21. Välj den typ av dokument som arbetaren har angett i fältet **I-9-dokumenttyp**.
22. Ange eller välj ett värde i fältet **Dokumentnummer**.
23. Välj **Spara**.

[!INCLUDE[footer-include](../../../../../includes/footer-banner.md)]
