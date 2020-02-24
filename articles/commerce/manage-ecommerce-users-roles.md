---
title: Hantera näthandelsanvändare och roller
description: I det här avsnittet beskrivs hur du ger användarna åtkomst till redigeringsmiljön för din Microsoft Dynamics 365 Commerce-webbplats.
author: bicyclingfool
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9a1f9abae20d0f2e71790a3b27337338dc042b52
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003543"
---
# <a name="manage-e-commerce-users-and-roles"></a>Hantera näthandelsanvändare och roller


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du ger användarna åtkomst till redigeringsmiljön för din Microsoft Dynamics 365 Commerce-webbplats.

Om du vill kontrollera användaråtkomst och bevilja användare behörighet att utföra särskilda uppgifter, använder du säkerhetsgrupper för webbplatsens redigeringsmiljö som du skapar i Microsoft Azure Active Directory (Azure AD). Du tilldelar först en ny eller befintlig säkerhetsgrupp från Azure AD till varje roll i redigeringsmiljön. Du kan sedan bevilja eller återkalla behörigheter för enskilda användare genom att antingen lägga till dessa användare i en lämplig säkerhetsgrupp eller ta bort dem från en säkerhetsgrupp.

## <a name="overview-of-roles-in-the-authoring-environment"></a>Översikt över roller i redigeringsmiljön

Dynamics 365 for Commerce redigeringsmiljön stöder följande roller.

| Roll                 | Beskrivning |
|----------------------|-------------|
| Systemadministratör | Användare med den här rollen har alla behörigheter för alla verktyg och för alla omdömen och recensioner. De kan också skapa webbplatser. |
| Administratör   | Användare med den här rollen har alla behörigheter för alla verktyg och RnR i en given webbplatsstruktur. |
| Webbtillverkare         | Användare med den här rollen kan skapa sidor, fragment och mallar, ladda upp och hantera tillgångar och utöka produkter och kategorier. |
| Läsare               | Användare med denna roll kan visa sidor, mallar, resurser, fragment, layouter och inställningar, men de kan inte göra ändringar. |
| RnR moderator        | Användare med denna roll kan moderera produktrecensioner. |

## <a name="system-administrator-role"></a>Systemadministratörroll

När du etablerar Dynamics 365 Commerce i Microsoft Dynamics Lifecycle Services (LCS)-miljön uppmanas du att ange en säkerhetsgrupp för rollen **Systemadministratör**. Den här rollen används sedan automatiskt på alla webbplatser som du skapar i den miljö som du konfigurerar. Säkerhetsgruppen för den här rollen kan bara uppdateras i LCS. På sidan **webbplatsadministration** för alla webbplatser visas den som skrivskyddad och endast i informationssyfte.

## <a name="administrator-role"></a>Administratörsrollen

När du skapar en ny webbplats i Commerce uppmanas du att ange en säkerhetsgrupp för rollen **administratör**. Se tabellen tidigare i det här avsnittet för en översikt över de behörigheter som den här rollen beviljar.

## <a name="add-or-update-security-groups"></a>Lägg till eller uppdatera säkerhetsgrupper

När webbplatsen har skapats kan bara användare som finns i de säkerhetsgrupper som är kopplade till rollerna **systemadministratör** och **administratör** få tillgång till redigeringsmiljön för den webbplatsen. Om du vill tilldela användare till rollerna **Webbtillverkare**, **RnR moderator** och **Läsare** måste du tilldela säkerhetsgrupper till dessa roller. Om du vill lägga till en säkerhetsgrupp till en roll, eller uppdatera en säkerhetsgrupp som för närvarande är tilldelad till en roll, följer du stegen nedan.

1. Gå till den webbplats som ska uppdateras.
1. I **webbplatshantering**, öppna sidan **säkerhet**.
1. Välj den roll du vill ändra.
1. Lägg till säkerhetsgrupper i roller eller ta bort säkerhetsgrupper från roller.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)

[Språkinformation för sökmotoroptimering (SEO) för din webbplats](search-engine-optimization-considerations.md)

[Hantera säkerhetspolicy för innehåll (CSP)](manage-csp.md)
