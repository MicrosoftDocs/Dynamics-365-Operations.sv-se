---
title: Tilldela användarroller för leasing
description: Det här ämnet beskriver de säkerhetsroller som används i Leasing av tillgångar. Det innehåller även information om hur du tilldelar användare till dessa roller.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 38c859d64742d582d0709506d83600ea26a21147
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878143"
---
# <a name="assign-lease-user-roles"></a>Tilldela användarroller för leasing

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver de säkerhetsroller som används i Leasing av tillgångar. Det innehåller även information om hur du tilldelar användare till dessa roller.

Tre användarroller differentierar åtkomsten till Leasing av tillgångar. En roll är lämplig för att underhålla leasing, en är lämplig för att visa leasing och en är lämplig att för att utföra en leasinghandläggares uppgifter. Varje roll har specifika behörigheter för alla leasingsidor, och varje användare kan visa, skapa, redigera och ta bort leasingar enligt sina arbetsuppgifter.

| Roll           | beskrivning |
|----------------|-------------|
| Upprätthålla leasing | Användare med den här rollen kan lägga till, redigera, ta bort och visa leasing. Den här rollen är utformad för dagliga användare vars uppgifter omfattar att skapa och bokföra månatliga journalposter och lägga till nya leasingar. Den här rollen ger till gång till alla funktioner i Leasing av tillgångar. |
| Visa leasing     | Användare med den här rollen kan bara visa leasingposter, planer och köra rapporter. De kan inte skapa nya leasingar, redigera befintliga leasingar eller skapa journalposter mot leasingar. Rollen är utformad för användare som bara behöver visa leasingar, leasingplaner och de transaktioner som inträffar mot dessa leasingar. |
| Leasinghandläggare    | Användare med den här rollen kan bara skapa nya leasingar. De kan inte redigera eller ta bort befintliga leasingar, visa leasingplaner eller bokföra leasingjournalposter. Den här rollen är avsedd för användare som arbetar i en datainmatningskapacitet. |

Följ dessa steg om du vill tilldela användarna roller som används i Leasing av tillgångar.

1. Gå till **Systemadministration \> Säkerhet \> Tilldela användare till roller**.
2. Välj rollen **Upprätthålla leasing**, **Leasinghandläggare** eller **Visa leasing** och välj sedan **Tilldela/exkludera användare manuellt**.
3. Välj användaren som du vill tilldela rollen och välj sedan **Tilldela till roll**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
