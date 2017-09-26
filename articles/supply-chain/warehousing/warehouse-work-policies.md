---
title: "Policyer för lagerarbete"
description: "Policyer för lagerställearbete styr om lagerställearbete skapas av lagerprocesser i produktionen, baserat på arbetsordertyp, lagerställe och produkt."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: 7612003bc20f91f173629893750478b034cff27b
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="warehouse-work-policies"></a>Policyer för lagerarbete

[!include[banner](../includes/banner.md)]


Policyer för lagerställearbete i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition styr om lagerställearbete skapas av lagerprocesser i produktionen, baserat på arbetsordertyp, lagerställe och produkt.

Denna arbetspolicy styr huruvida arbetsuppgifter på lagerstället skapas för lagerställeprocesser inom tillverkningen. Du kan ställa in arbetspolicyn genom att använda en kombination av **arbetsordertyper**, en **lagerplats** samt en **produkt** Exempelvis rapporteras produkt L0101 som färdig till utleveransplats 001. Den färdiga varan förbrukas senare i en annan produktionsorder på utleveransplats 001. I det här fallet kan du ställa in en arbetspolicy för att förhindra arbete för inlagring av färdiga varor skapas när du rapporterar produkt L0101 som färdig till utleveransplats 001. Arbetspolicyn är en enskild enhet som kan beskrivas genom följande information:

-   **Arbetspolicynamn**(den unika identifieraren för arbetspolicyn)
-   **Arbetsordertyper** och **Metod för skapande av arbetsuppgift**
-   **Lagerplatser**
-   **Produkter**

## <a name="work-order-types"></a>Typer av arbetsorder
Du kan välja bland följande arbetsuppgifter:

-   Plats för slutförda varor
-   Plats för samprodukt och biprodukt
-   Råmaterialhämtning

Fältet **Metod för att skapa arbete** har värdet **Aldrig**. Det här värdet anger att arbetspolicyn förhindrar att arbetsuppgifter på lagerstället skapas för vald arbetsordertyp.

## <a name="inventory-locations"></a>Lagerplatser
Du kan välja en plats som arbetspolicyn gäller för. Om ingen plats finns associerad med en arbetspolicy, gäller inte arbetspolicyn för några processer. På sidan **Locations** kan du också välja eller avbryta valet av arbetspolicy för en viss plats.

## <a name="products"></a>Produkter
Du kan välja en produkt som arbetspolicyn gäller för. Du kan använda arbetspolicyn antingen på alla produkter eller på utvalda produkter.

## <a name="example"></a>Exempel
I följande exempel finns det två produktionsorder, PRD-001 och PRD-00*2*. Produktionsorder PRD-001 har en åtgärd med namnet **Sammansättning**, där produkten SC1 rapporterats som färdig till plats O1. Produktionsorder PRD-002 har en åtgärd med namnet **Painting** och förbrukar produkten SC1 från platsen O1. Produktionsorder PRD-002 förbrukar även råmaterial RM1 från platsen O1. RM1 lagras på lagerställeplats och BULK-001 och plockas till platsen O1 av lagerställets arbetsuppgift för plockning av råmaterial. Plockningsarbetet skapas när produktion PRD-002 frisläpps. 

[![Policyer för lagerarbete](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png) 

När du planerar att konfigurera en arbetspolicy för detta scenario på lagerstället, bör du beakta följande information:

-   Arbetsuppgifter för förvaring av färdiga varor på lagerställen krävs inte när du rapporterar produkten SC1 som färdig från produktionsorder PRD-001 till platsen O1. Detta eftersom åtgärden **Painting** för produktionsorder PRD-002 förbrukar SC1 på samma plats.
-   Lagerställearbete för plockning av råmaterial krävs för att flytta råmaterialet RM1 från lagerplats BULK-001 till plats O1.

Här följer ett exempel på en arbetspolicy som du kan ställa in, baserat på dessa överväganden.

|                                         |                                                       |
|-----------------------------------------|-------------------------------------------------------|
|**Namn på arbetspolicy**<br>                 |**Typer av arbetsorder**<br>                               |
| Lagringsfri 01                    |- Lagring av färdig vara<br>                           |
|                                         |**Platser**<br>                                      |
|                                         |- O1   |                                               |
|                                         |**Produkter** <br>                                      |
|                                         |- SC1                                                  |

Följande procedurer innehåller steg-för-steg-instruktioner om hur du ställer in arbetspolicyn för lagerstället för detta scenario. En exempelinställning som visar hur du rapporterar en produktionsorder som slutförd till en plats som inte kontrolleras via registreringsskylt beskrivs också.

## <a name="set-up-a-warehouse-work-policy"></a>Konfigurera en policy för lagerarbete
Lagerställeprocesser inkluderar inte alltid lagerarbete. Genom att definiera en arbetspolicy kan du förhindra skapande av arbete för råmaterialhämtning och inlagring av färdiga varor för en uppsättning av produkter på specifika platser. Demonstrationsdataföretaget USMF har använts för att skapa denna procedur. 

STEG (21)

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| 1.  | Gå till Lagerstyrning &gt; Inställningar &gt; Arbete &gt; Arbetspolicyer.        |
| 2.  | Klicka på Ny.                                                                 |
| 3.  | Skriv in "Inget inlagrat arbete" i fältet Namn på arbetspolicy.                    |
| 4.  | Klicka på Spara.                                                                |
| 5.  | Klicka på Lägg till.                                                                 |
| 6.  | Markera vald rad i listan.                                        |
| 7.  | Skriv in "Plats för slutförda varor" i fältet Typ av arbetsorder.            |
| 8.  | Klicka på Lägg till.                                                                 |
| 9.  | Markera vald rad i listan.                                        |
| 10. | Välj ”Plats för samprodukt och biprodukt” i fältet Typ arbetsorder. |
| 11. | Visa avsnittet Lagerplatser.                                    |
| 12. | Klicka på Lägg till.                                                                 |
| 13. | Markera vald rad i listan.                                        |
| 14. | Ange ”51" i lagerställets lista.                                         |
| 15. | Ange eller välj "001" i fältet Plats.                              |
| 16. | Expandera avsnittet Produkter.                                               |
| 17. | Välj "Markerad" i fältet Produktval.                         |
| 18. | Klicka på Lägg till.                                                                 |
| 19. | Markera vald rad i listan.                                        |
| 20. | Ange eller välj "L0101" i fältet Artikelnummer.                         |
| 21. | Klicka på Spara.                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Rapportera en produktionsorder som slutförd till en plats som inte kontrolleras via registreringsskylt
Denna procedur visar ett exempel på rapportering som slutförd till en plats som inte kontrolleras via registreringsskylt. En tillämplig arbetspolicy är förutsättningen är den här uppgiften. Föregående procedur anger arbetspolicyns konfiguration. 

STEG (25)

<table>
<tbody>
<tr>
<td colspan="3"><strong>Deluppgift: Ställ in en utleveransplats.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Gå till Organisationsadministration &gt; Resurser &gt; Resursgrupper.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Välj resursgrupp "5102" i listan.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Klicka på Redigera.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>Ange "51" i fältet Utleveranslagerställe.</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>Ange "001" i fältet Utleveransplats.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>Plats 001 är en ej ID-nummertyrd plats. Du kan ställa in en plats för ej ID-nummertyrd utleveransplats bara om en lämplig arbetspolicy finns för platsen.</td>
</tr>
<tr>
<td colspan="3"><strong>Deluppgift: Skapa en produktionsorder och rapportera den som färdig.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Stäng sidan.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Gå till Produktionskontroll &gt; Produktionsorder &gt; Alla produktionsorder.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Klicka på Ny produktionsorder.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>Ange ett artikelnummer i fältet "L0101".</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>Klicka på Skapa.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>Klicka på Produktionsorder i åtgärdsfönstret.</td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td>Klicka på Uppskattning.</td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td>Klicka på OK.</td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td>Klicka på Start.</td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td>Klicka på fliken Allmänt.</td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td>Välj "Aldrig" i fältet Automatisk strukturlisteförbrukning.</td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td>Klicka på OK.</td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td>Klicka på Rapportera som färdigt.</td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td>Klicka på fliken Allmänt.</td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td>Välj Ja i fältet Godkänn fel.</td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td>Klicka på OK.</td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td>Klicka på Lagerställe i åtgärdsfönstret.</td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td>Klicka på Information om arbete.</td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td>När tillverkningsordern rapporterades som färdig, genererades inget arbete för plats. Detta inträffar, eftersom en arbetspolicy definieras som hindrar arbete från att genereras när produkten L0101 rapporterats som färdig till plats 001.</td>
</tr>
</tbody>
</table>




