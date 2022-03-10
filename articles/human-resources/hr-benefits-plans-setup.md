---
title: Skapa en förmånsplan
description: I detta ämne beskrivs hur du konfigurerar förmånsplaner i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitPlanListPage, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7d3163bf30af9ed0eac2c753ed4aabb15d568ff4
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065336"
---
# <a name="create-a-benefit-plan"></a>Skapa en förmånsplan


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I detta ämne beskrivs hur du konfigurerar förmånsplaner i Dynamics 365 Human Resources.

1. I arbetsytan **Hantering av förmåner** under **Planer**, välj **förmånsplaner**.

2. Välj **Ny**.

3. På fliken **Allmänt**, ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Plan** | En unik identifierare för planen. |
   | **Beskrivning** | En beskrivning av planen. |
   | **Plantyp** | När du skapar en ny plan måste du ange plantypen. En plantyp är en grupp på hög nivå med specifika typer av förmåner. Varje plantyp anger om en medarbetare kan registreras i flera planer av den typen, anger om kontakter är mottagare eller beroende och definierar omfattningsalternativ. Du kan skapa nya anpassade plantyper som uppfyller behoven hos dina förmånserbjudanden. Huvudsakliga underhållsplaner är: <ul><li>401K</li><li>LÄGG TILL</li><li>Tandvård</li><li>Lämplighet</li><li>FSA</li><li>Livförsäkring</li><li>LTD</li><li>Sjukvård</li><li>PTO</li><li>STD</li><li>Vision</li></ul> |
   | **Kod för plantyp** | Plantypkoden för plantypen. |
   | **Program** | Anger ett program som du vill tilldela planen till. |
   | **Bunt** | Anger en bunt som du vill tilldela planen till. |
   | **Rubrik** | Anger om planen är huvudplan i den bunt den är tilldelad till. |
   | **Giltig från datum och tid** | Datum och tid som planen startar. Standardvärdet är det aktuella systemdatumet. |
   | **Giltig till datum och tid** | Datum och tid som planen slutar. Standardvärdet är 12/31/2154, vilket betyder aldrig. |

4. På fliken **Konfiguration**, ange värden för följande fält, beroende på vilken typ av plan du skapar:

   | Plantyp | Fält | Beskrivning |
   | --- | --- | --- |
   | Medicinsk (medicinsk, tandvård, syn, HMO) | COBRA | Anger om planen är COBRA-berättigad (Consolidated Omnibus Budget Reconciliation Act). |
   | Medicinsk (medicinsk, tandvård, syn, HMO) | HIPAA | Anger om planen är HIPAA-berättigat (Health Insurance Portability and Accountability Act). |
   | Medicinsk (medicinsk, tandvård, syn, HMO)<br><br>Annat (PTO, lämplighet)<br><br>Annat<br><br>Långvarig funktionsnedsättning<br><br>Lägg till (enkel liv, frivillig liv)<br><br>Besparingar (t.ex. 401(k))<br><br>FSA | Berättigat före skatt | Anger om avgifter kan göras till planen innan moms tillämpas. |
   | Medicinsk (medicinsk, tandvård, syn, HMO)<br><br>Annat (PTO, lämplighet)<br><br>Långvarig funktionsnedsättning<br><br>Lägg till (enkel liv, frivillig liv)<br><br>Besparingar (t.ex. 401(k))<br><br>FSA | Berättigat efter skatt | Anger om avgifter kan göras till planen efter moms tillämpas. |
   | Medicinsk (medicinsk, tandvård, syn, HMO)<br><br>Annat (PTO, lämplighet)<br><br>Långvarig funktionsnedsättning<br><br>Lägg till (enkel liv, frivillig liv)<br><br>Besparingar (t.ex. 401(k))<br><br>FSA | Deltagare | Anger vem som bidrar till planen – medarbetaren, arbetsgivaren eller båda. |
   | Långvarig funktionsnedsättning<br><br>Lägg till (enkel liv, frivillig liv) | Minimal omfattning | Minsta belopp för försäkringsskydd som krävs för planen. |
   | Långvarig funktionsnedsättning<br><br>Lägg till (enkel liv, frivillig liv) | Maximal omfattning | Högsta belopp för försäkringsskydd som krävs för planen. |
   | Långvarig funktionsnedsättning<br><br>Lägg till (enkel liv, frivillig liv) | Använd ökningar av försäkringsbeloppet | Anger om du vill validera att försäkringsbeloppet matchar ett giltigt stegvist belopp. |
   | Långvarig funktionsnedsättning<br><br>Lägg till (enkel liv, frivillig liv) | Stegvist belopp | Det stegvisa beloppet för försäkringsskydd för planen. Om till exempel det stegvisa beloppet är 1 000 kan en medarbetare inte ha en försäkring på 200 500 $, men de måste avrunda upp till 201 000 $ eller ned till 200 000 $. |
   | Långvarig funktionsnedsättning<br><br>Lägg till (enkel liv, frivillig liv) | Stegvis riktning | Anger riktningen för avrundning – antingen uppåt eller nedåt – när försäkringsbeloppet inte uppfyller värdet för stegvist belopp. |
   | Lägg till (enkel liv, frivillig liv) | Bevis på försäkringsbarhet | Anger om en medarbetare måste tillhandahålla bevis på försäkringsbarhet. |
   | Lägg till (enkel liv, frivillig liv) | Tid | Belopp i redovisningsvaluta. Detta fält är endast aktivt om kryssrutan Bevis på försäkringsbarhet är markerad. |
   | Besparingar (t.ex. 401(k))<br><br>FSA | Lägsta årliga tillägg | Minsta tilläggsbelopp som krävs för planen. |
   | Besparingar (t.ex. 401(k))<br><br>FSA | Högsta årliga tillägg | Högsta tilläggsbelopp som krävs för planen. |
   | Besparingar (t.ex. 401(k)) | Arbetsgivarens maximala årliga belopp | Det högsta belopp som en arbetsgivare får delta i mot en plan för medarbetarens besparingar under en förmånsperiod. Du måste markera kryssrutan för arbetsgivarens matchning för att kunna använda det här fältet. |
   | Besparingar (t.ex. 401(k)) | Arbetsgivarmatchning | Anger om arbetsgivaren bidrar till en anställds besparingsplan. |
   | Besparingar (t.ex. 401(k)) | Arbetsgivarens matchningsprocent | Den procentandel av en medarbetares bidrag som arbetsgivaren kommer att matcha. |
   | Besparingar (t.ex. 401(k)) | Maximal arbetsgivarmatchning | Ange den högsta procentandel som arbetsgivaren matchar. Om en arbetsgivare till exempel ska matcha 100 % av medarbetarens bidrag upp till 6 % av medarbetarens lön, är arbetsgivarens matchning 6 %. |

5. På fliken **Inställningar**, ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Tillåt/fortsätt anmälan** | Anger om medarbetarna kan registrera sig i planen om de uppfyller berättigandekraven.</br></br>Om detta är inställt på Nej blir planen inte tillgänglig för medarbetare när du bearbetar berättiganden. |
   | **Anmäl automatiskt från föregående år** | Anger om en berättigad medarbetare automatiskt ska anmälas till planen om den anställda har anmälts under föregående år. |
   | **Anmäl automatiskt som standard** | Anger om du vill välja planen för registrering som standard. Planen är inte obligatorisk, så medarbetaren kan ändra standardurvalet. |
   | **Stängd för nya anmälningar** | Anger om planen ska begränsas till endast berättigade anställda som ingick i planen året innan. |
   | **Obligatorisk plan** | Anger om medarbetarna ska registreras automatiskt i planen. Medarbetare kan inte ändra anmälans val. |
   | **Startdatum** | Det datum då planen skapades i företaget. |
   | **Leverantörskonto** (förmånsleverantör) | Den leverantör som företaget betalar bonus för i planen. |
   | **Namn** (förmånsleverantör) | Namn på leverantören. |
   | **Leverantörsreferens** (förmånsleverantör) | Leverantörens referens för planen. Till exempel företagets grupplannummer. |
   | **Alternativ referens** (förmånsleverantör) | Leverantörens alternativa referens för planen. Till exempel företagets kontonummer. |
   | **Valuta** (förmånsleverantör) | Den valuta som används för att betala ut bonusar till leverantören. |
   | **Utgiftskonto** (förmånsleverantör) | Det redovisningskonto som används som utgiftskonto för planbonusar. |
   | **Leverantörskonto** (förmånsadministratör) | Den leverantör som företaget administrera planen. Om planen är självadministrerad lämnar du det här fältet tomt. |
   | **Namn** (Förmånsadministratör) | Namnet på leverantören av förmånsadministratören. |
   | **Leverantörsreferens** (förmånsadministratör) | Leverantörens administratörsreferens för planen. |
   | **Alternativ referens** (förmånsadministratör) | Leverantörens alternativa referens för planen. |
   | **Valuta** (Förmånsadministratör) | Den valuta som används för att betala ut förmånsadministratörer. |
   | **Utgiftskonto** (förmånsadministratör) | Det redovisningskonto som används som utgiftskonto för de kostnader som är associerade med administration av planen. |

6. Filtrera efter behov på fliken **filter**. Du kan filtrera efter följande fält:

   - **Affärsenhet**
   - **Avdelning**
   - **Juridisk person**
   - **Plats**
   - **Befattning**

7. På fliken **Berättiganderegler**, ange värden för följande fält:

   | Fält | Beskrivning |
   | --- | --- |
   | **Radnummer** | Avtalets radnummer för berättiganderegeln. |
   | **Berättiganderegel** | En berättiganderegel som ska tillämpas på förmånsplanen. Den här berättiganderegeln för kommer att tillämpas på motsvarande åtgärdstyp och är associerad med den angivna vänteperiod för försäkringen och avdrag. |
   | **Åtgärdstyp** | Åtgärden för att tillämpa berättiganderegeln på: förmånsanmälan eller förmånsutgång. |
   | **Vänteperiod för försäkringen** | Ett värde från formuläret väntetider. Vänteperiod för försäkringen är det antal dagar eller månader en medarbetare väntar på att få förmånsdisponeringen eller förmånsutgång baserat på kriterierna i regeln och åtgärdstypen för berättigande. |
   | **Vänteperiod för avdrag** | Ett värde från formuläret väntetider. Vänteperiod för avdrag är det antal dagar eller månader en medarbetare väntar på att få förmånsavdrag från deras lön baserat på kriterierna i regeln och åtgärdstypen för berättigande. |

8. Välj **Spara**.

## <a name="view-enrolled-workers"></a>Visa anmälda medarbetare

DU kan visa de medarbetare som är anmälda i den valda förmånsplanen.

1. I arbetsytan **Hantering av förmåner** under **Planer**, välj **förmånsplaner**.

2. På fliken **Förmåner** i navigeringsfältet väljer du **Anmälda medarbetare**.

## <a name="attach-coverage-options"></a>Bifoga täckningsalternativ

Du kan lägga till omfattningsalternativ för den valda förmånsplanen. Om du kopplar omfattningsalternativ får du inställningarna för tariff och avdrag för omfattningsalternativ.  Exempel: för en medicinsk plan skulle användaren välja ett alternativ för familjeomfattning.  De måste sedan välja familjetariffen för den associerade planen (anges i tariffinställning) och avdraget för den associerade planen (anges i tariffinställning). Detta ger kostnaden för arbetsgivaren och medarbetaren för en vald omfattning. Sedan upprepar du processen för en medarbetare+1 omfattning eller medarbetaromfattning.

1. I arbetsytan **Hantering av förmåner** under **Planer**, välj **förmånsplaner**.

2. På fliken **Förmåner** i navigeringsfältet väljer du **Bifoga omfattningsalternativ**.

## <a name="override-eligibility-rules"></a>Åsidosätt berättiganderegler

Du kan lägga till medarbetare till en plan som undantag till reglerna för berättigande. Varje arbetstagare som du lägger till är berättigad till förmånsplanen.

1. I arbetsytan **Hantering av förmåner** under **Planer**, välj **förmånsplaner**.

2. På fliken **Förmåner** i navigeringsfältet väljer du **Åsidosätt berättiganderegel**.

## <a name="view-attached-periods"></a>Visa kopplade perioder

Du kan se en lista över tillgängliga förmånsperioder.

1. I arbetsytan **Hantering av förmåner** under **Planer**, välj **förmånsplaner**.

2. Klicka på fliken **Perioder** i navigeringsfältet.

## <a name="view-plan-description"></a>Visa planbeskrivningen

Du kan ge en beskrivning av planen för att hjälpa de medarbetare som har urval av deras förmåner. Den planbeskrivning som du anger här visas i Självbetjäning för medarbetare när du hovrar över planen i listan med omfattningsalternativ.

1. I arbetsytan **Hantering av förmåner** under **Planer**, välj **förmånsplaner**.

2. På fliken **Förmåner** i navigeringsfältet väljer du **Planbeskrivning**.

## <a name="view-flex-credit-programs"></a>Visa flexkreditprogram

1. I arbetsytan **Hantering av förmåner** under **Planer**, välj **förmånsplaner**.

2. På fliken **Förmåner** i navigeringsfältet väljer du **Flexkreditprogram**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
