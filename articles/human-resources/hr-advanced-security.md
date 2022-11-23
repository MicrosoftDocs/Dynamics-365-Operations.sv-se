---
title: Begränsa åtkomsten till arbetare per juridisk person
description: I den här artikeln förklaras hur du ställer in arbetsåtkomst per juridisk person.
author: twheeloc
ms.date: 11/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fadd2c34d31bbd259255596c06a8e7517f7a774b
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780399"
---
# <a name="restrict-access-to-workers-by-legal-entity"></a>Begränsa åtkomsten till arbetare per juridisk person

I den här artikeln förklaras hur du ställer in arbetsåtkomst per juridisk person.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Medarbetare är anställda i juridiska personer. Nedan följer några exempel:

- Aaron Con är anställd i den juridiska personen USSI.
- Ahmed Barnett är anställd i den juridiska personen USMF.
- Alicia Thornber är anställd i de juridiska personerna GLSI och USMF.

Beroende på vilken roll en användare har i företaget kanske användaren måste ha åtkomst till alla medarbetare inom alla juridiska personer. En användare kanske måste begränsas så att han eller hon bara kan visa medarbetare i den juridiska person som han eller hon ska ha åtkomst till. För att kontrollera vilka anställda en användare kan se, välj parametern **Begränsa åtkomsten till arbetarinformation** på sidan **Personal delade parametrar**.

En användare har till exempel tillgång till sidan **Arbetare** och bara tillgång till den juridiska personen USMF. I detta fall kan användaren visa följande information för medarbetarna i den föregående listan:

- Om funktionen för att begränsa åtkomsten till arbetsinformation inte är aktiverad kan användaren visa information för Aaron, Ahmed och Alicia.
- Om funktionen är aktiverad kan användaren endast se information för Alicia och Ahmed, eftersom de också är anställda i USMF juridiska person.

Vilken information som visas varierar beroende på vilket program du använder.

## <a name="dynamics-365-human-resources-stand-alone"></a>Dynamics 365 Human Resources fristående

Om funktionen för att begränsa åtkomsten till arbetsinformation har aktiverats, visas ett tomt värde för den begränsade användaren i vissa listor som innehåller arbetarens namn.

Till exempel kommer en användare som endast har åtkomst till den juridiska enheten USMF att uppleva följande beteende:

- I listan **Aktiva befattningar** kommer kolumnen **Arbetare** kommer att vara tom för Aarons position, eftersom användaren inte har tillgång till anställda i den juridiska enheten USSI.
- Om användaren går ner i arbetarens namn visas en tom sida för **Arbetare**.

## <a name="dynamics-365-human-resources-on-finance-infrastructure"></a>Dynamics 365 Human Resources i ekonomi infrastruktur

Om funktionen för att begränsa åtkomsten till arbetsinformation har aktiverats, visas ett tomt värde för den begränsade användaren kommer att se arbetarens namn i vissa listor.

Till exempel kommer en användare som endast har åtkomst till den juridiska enheten USMF att uppleva följande beteende:

- I listan **Aktiva befattningar** visar kolumnen **Arbetare** Aarons namn. Om användaren hovrar över arbetarens namn visas bara namnet och titeln.
- Om användaren går ner i arbetarens namn visas en tom sida för **Arbetare**.

> [!TIP]
> Om du använder Dynamics 365 Human Resources på finansinfrastruktur och vill att begränsade användare ska se tomma värden för arbetarnamn kan du lägga till **Begränsa åtkomst till arbetare** säkerhetsbehörighet till användarrollerna på sidan **Säkerhetskonfiguration**.

När du har aktiverat funktionen måste du utföra några extra steg för att ställa in behörigheter för varje användare vars vy måste begränsas.

1. Markera en användare på sidan **Användare**.
2. Välj en roll för användaren. Alternativet **Tilldela organisationer** blir tillgängligt.
3. Markera **Tilldela organisationer**.
4. På den nya sidan väljer du **Bevilja åtkomst till specifika organisationer enskilt** och välj sedan de organisationer som användaren ska få åtkomst till.
5. Upprepa steg 2 till 4 för alla andra roller som användaren har, inklusive systemanvändarrollen.

> [!NOTE]
> De juridiska personer som en användare har åtkomst till måste matcha alla användarens roller.
