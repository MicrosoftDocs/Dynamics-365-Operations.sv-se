---
title: Översikt över plantyper
description: En plantyp i Microsoft Dynamics 365 Human Resources är en grupp på hög nivå med specifika typer av förmåner.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2eb8ecdd849aa2f583202ac2ec7c3e1bb06698a1
ms.sourcegitcommit: a8ac6d9b63eb67d14dd17a086ef4f1eccd7f9fc1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2021
ms.locfileid: "7431421"
---
# <a name="plan-type-overview"></a>Översikt över plantyp

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En plantyp är en grupp på hög nivå med specifika typer av förmåner. Varje plantyp har en plantypkod som bestämmer regler för plantypen. Till exempel plantypen **Enkel liv** kommer att ha plantypkoden **Liv** eftersom det är en typ av livförsäkringsplan och måste överensstämma med regler som har fastställts för plantypkoden **Liv**. En annan plantyp kan vara **Tillägg liv**.  Den här plantypen innehåller också plantypkoden **Liv**.

Varje plantyp visar om en medarbetare kan registreras i en plan av dess typ eller flera. En medarbetare skulle t.ex. kunna registrera både policyn **Enkelt liv** och policyn **Tillägg liv** för plantypen Liv. En medarbetare är sannolikt tillåten att registrera i endast en policy av typen sjukvård.

Om en plantyp omfattar kontakter anger plantypen om kontakter är mottagare eller beroende. Plantypen **Enkelt liv** kan exempelvis ha mottagare medn plantypen Enkel medicinsk har beroende. I vissa fall kanske en plan inte har några personliga kontakter. Till exempel ett flexibelt utgiftskonto eller parkeringsbidrag.


En plantyp kan definiera täckningsalternativ. Täckningsalternativen definieras på sidan **Disponeringsalternativ**. Ett alternativ för disponering kan ange förmånsbeloppet eller de kontakter som är berättigade till plantypen. Om kontakttypen till exempel är **Mottagare**, ska täckningsalternativet definiera villkoren för vad mottagaren är berättigad till när förmånen används. Om kontakttypen är **Beroende** ska täckningsalternativet definiera relationen mellan beroende och medarbetaren. 

> [!IMPORTANT]
> Sidan **Plantyper** innehåller nyckeldata som påverkar vilka alternativ som är tillgängliga när en ny förmånsplan skapas:
>
> - **Plantypkod** – Det här fältet påverkar vad som visas på fliken **Konfiguration** när den faktiska förmånen ställs in.  
> - **Samtidig anmälan** – Det här fältet avgör om flera anmälningar är tillåtna. (För en medicinsk plan ställs det här fältet normalt in på **En anmälan**.)
> - **Kontakttyp** – Detta fält gör att beroende kan läggas till i en plan. Om den anges till **Ingen**, anställda som anmäler sig till förmåner har inte möjlighet att välja vare sig en förmånstagare eller en beroende.
> - **Disponeringsalternativ** – Använd det här fältet om du vill koppla disponeringsalternativen till plantyperna. Det definierar antingen vilka personer som omfattas av den här plantypen eller disponeringsbeloppen som är tillgängliga för den här plantypen. Du kan till exempel ange att endast medarbetaren, medarbetaren och en annan person ska ha tillgång till täckning för en medicinsk plantyp, eller medarbetaren och deras familj.

## <a name="create-plan-types"></a>Skapa plantyper

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
