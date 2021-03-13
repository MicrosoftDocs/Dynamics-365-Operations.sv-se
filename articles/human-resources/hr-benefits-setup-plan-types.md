---
title: Skapa plantyper
description: En plantyp i Microsoft Dynamics 365 Human Resources är en grupp på hög nivå med specifika typer av förmåner. Varje plantyp har en plantypkod som bestämmer regler för plantypen.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e24c11fb6e84a7480a40b706b106cd8465470f5c
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114291"
---
# <a name="create-plan-types"></a>Skapa plantyper

En plantyp i Microsoft Dynamics 365 Human Resources är en grupp på hög nivå med specifika typer av förmåner. Varje plantyp har en plantypkod som bestämmer regler för plantypen. Exempel: den grundläggande plantypen enkelt liv skulle ha plantypkoden liv eftersom den är en typ av livförsäkringsplan och måste följa reglerna för plantypkoden för liv. En annan plantyp kan vara tillägg liv, även med plantypkod liv.

Varje plantyp visar om en medarbetare kan registreras i en plan av dess typ eller flera. En medarbetare skulle t.ex. kunna registrera både policyn enkel liv och den tillägg liv cykeln för plantypen liv. En medarbetare är sannolikt tillåten att registrera i endast en policy av typen sjukvård.

Om en plantyp omfattar kontakter anger plantypen om kontakter är mottagare eller beroende. En t.ex. plantypen enkel liv har mottagare, medan en grundläggande sjukvårdsplantyp skulle ha beroenden. I vissa fall kanske en plan inte har några personliga kontakter. Till exempel ett flexibelt utgiftskonto eller parkeringsbidrag.

En plantyp kan definiera täckningsalternativ. Alternativen för disponering är definierade i formuläret täckningsalternativ. Ett alternativ för disponering kan ange förmånsbeloppet eller de kontakter som är berättigade till plantypen. Om kontakttypen till exempel är mottagare, ska täckningsalternativet definiera villkoren för vad mottagaren är berättigad till när förmånen används. Om kontakttypen är beroende ska täckningsalternativet definiera relationen mellan beroende och medarbetaren. 

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **plantyper**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | **Plantyp** | Ett unikt namn som identifierar plantypen. |
   | **Beskrivning** | En beskrivning av plantypen. |
   | **Kod för plantyp** | Välj en kod för plantyp från listrutan med värden. I listan med kod för plantyp visas alla plantyper som stöds i den aktuella versionen. |
   | **Samtidig anmälan** | Anger om en medarbetare kan registrera flera förmånsplaner av samma plantyp eller endast en förmånsplan per plantypen. |
   | **Kontakttyp** | Anger rollen för personalkontakten. Värdena är tomma, beroende och mottagare. Du kan lämna **kontakttypen** tom om deras plantyp inte kräver en beroende eller mottagare som baseras på omfattningsalternativ. |

4. Om du vill konfigurera livshändelsealternativ väljer du **åtgärder** och väljer sedan **alternativ för livshändelser**. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | **Plantyp** | Plantypen för att konfigurera livshändelsealternativ för. |
   | **ID för livshändelsetyp** | ID för livshändelsetypen. |
   | **Tillåt annullering** | Anger om en medarbetare kan annullera en förmånsplan under en livshändelse. |
   | **Ändra omfattningsalternativ** | Anger om en medarbetare kan ändra omfattningsalternativ under en livshändelse. |
   | **Ändra till en ny plan** | Anger om en medarbetare kan ändra planer under en livshändelse. |
   | **Annullera plan automatiskt** | Anger om planen ska annulleras automatiskt under livshändelsen. |
   | **Öppna berättigandekontrollen igen automatiskt** | Anger om berättigandekontrollen av förmånsanmälan automatiskt ska öppnas igen under livshändelsen. |
   | **Rapportfönster** | Anger rapportfönstret, i dagar, för livshändelsen. **Obs**! om du inte anger ett belopp, förutsätts att rapportfönstret är noll och livshändelsen bearbetas inte. |

5. Välj **Spara**. 
