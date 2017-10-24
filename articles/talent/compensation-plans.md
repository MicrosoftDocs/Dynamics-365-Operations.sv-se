---
title: Kompensationsplaner
description: "Kompensations- och förmånschefer kan använda kompensationshantering för att underhålla och bearbeta fasta och variabla kompensationsplaner för organisationens medarbetare."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5a24ccf124d1f3a078fe98b90301597f70bc41c4
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="compensation-plans"></a>Kompensationsplaner

[!include[banner](includes/banner.md)]


Kompensations- och förmånschefer kan använda kompensationshantering för att underhålla och bearbeta fasta och variabla kompensationsplaner för organisationens medarbetare.

### <a name="introduction"></a>Introduktion

Kompensationshantering används för att styra du utbetalningen av grundlön och belöningar. En medarbetares fasta grundlön och merithöjningar kontrolleras genom fasta kompensationsplaner. Betalningen av incitament, till exempel bonusar, resultatbelöningar, aktieoptioner och anslag och även engångsbelöningar kontrolleras genom variabla kompensationsplaner. 

Medarbetare kan registreras i en eller flera planer av båda typerna. En medarbetare måste uppfylla följande krav för att kunna registreras i en kompensationsplan:
-   Medarbetaren måste ha en aktiv befattningstilldelning.
-   Medarbetaren måste uppfylla villkoren som definieras av berättiganderegler för en kompensationsplan.

## <a name="compensation-setup"></a> Kompensationskonfiguration
Följande register visar komponenter i kompensationsprocessen som kan vara väsentliga i konfigurationen av ditt företags kompensationsplaner.

<table>
<thead>
<tr class="header">
<th>Komponent</th>
<th>Mer information …</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Åtgärder för fast kompensation</td>
<td>Fasta kompensationsåtgärder åstadkommer två syften:
<ul>
<li>Åtgärder kan ange den typ av information som måste registreras när en medarbetares kompensation ändras. Du kan till exempel kräva att orsaken till en ändring, till exempel en kampanj eller en degradering registreras.</li>
<li>Åtgärder kan se till att en beräkning används när fasta kompensationsplaner bearbetas.  Exempelvis jämför åtgärder av typen Eget kapital medarbetarens lön med den minsta referenspunkten för medarbetarens nivå och ser till att medarbetaren får minst minimibeloppet betalt.</li>
</ul></td>
</tr>
<tr class="even">
<td>Nivåer</td>
<td>Nivåerna är associerade med olika jobb, och eventuella befattningar som är relaterade till en jobbreferens. Du kan skapa diskreta nivåer för de tre typerna av kompensationsplaner: Grad, Band och Steg.</td>
</tr>
<tr class="odd">
<td>Matris för utnyttjande inom löneintervall</td>
<td>En intervallutnyttjandematris hjälper dig att migrera medarbetare till kontrollpunkten för deras jobb. Du kan också använda intervallutnyttjandematrisen om du vill styra lönekapitalet inom företaget utan hänsyn till en enskild medarbetares prestanda eller företagets generella prestanda. Lägre betalda medarbetare i intervallet får exempelvis procentuellt större ökningar än de som har en högre lön inom intervallet. På så sätt kan du systematiskt motboka skillnader i eget kapital. Intervallutnyttjandet beräknas på följande sätt: (Fast lönesats - Minsta intervallvärde) ÷ (Högsta intervallvärde - Minsta intervallvärde).</td>
</tr>
<tr class="even">
<td>Referenspunktsinställningar</td>
<td>Referenspunktsinställningar omfattar ett antal referenspunkter som motsvarar intervallen i en lönesatsmatris. Varje intervall kan associeras med en lönesats. Till exempel har gradplaner ofta referenspunkter för minimum, mittpunkt och maximum.</td>
</tr>
<tr class="odd">
<td>Kompensationsmatris</td>
<td>En kompensationsmatris är en uppsättning referenspunkter och nivåer som du använder för att skapa en kompensationsstruktur.</td>
</tr>
<tr class="even">
<td>Kompensationsstruktur</td>
<td>En kompensationsstruktur är en kompensationsmatris som har lönesatser kopplade till referenspunkterna för varje nivå.</td>
</tr>
<tr class="odd">
<td>Berättiganderegler</td>
<td>Berättiganderegler används för att identifiera medarbetare i specifika jobb, jobbfunktioner, jobbtyper, avdelningar, fackföreningar eller kompensationsområden som täcks av specifika kompensationsplaner. Du måste skapa berättiganderegler för både fasta och variabla kompensationsplaner när du vill anmäla medarbetare till planen. När du har angett berättiganderegler för en kompensationsplan kan du definiera vilka nivåer som ska tillämpas på jobben som omfattas av planen.</td>
</tr>
<tr class="even">
<td>Lönefrekvenser</td>
<td>Lönefrekvenser används för att definiera den tidsperiod för vilken kompensationen anges.  Till exempel hjälper lönefrekvensen dig att förstå huruvida kompensationsbeloppet anges som en årslön kontra en timlön. Lönefrekvenser används också för att ställa in konverteringsfaktorer om du vill konvertera kompensationsbelopp från månadslön, veckolön, varannanveckaslön och timlön till en årlig lönefrekvens.</td>
</tr>
<tr class="odd">
<td>Kompensationsregioner</td>
<td>Kompensationsområden används för att ange medarbetarkompensation baserat på var arbetsplatsen ligger.</td>
</tr>
<tr class="even">
<td>Kontrollpunkt</td>
<td>Kontrollpunkten anger vad du anser vara den ideala lönesatsen för alla medarbetare på en viss kompensationsnivå. För gradplansstrukturer utgörs kontrollpunkterna vanligtvis av intervallernas mittpunkt. Bandstrukturer använder sällan kontrollpunkter. Du kan ange kontrollpunkten för en fast kompensationsplan i formuläret Planer för fast kompensation.</td>
</tr>
<tr class="odd">
<td>Jobbfunktioner</td>
<td>Jobbfunktioner används för att klassificera och filtrera kompensationsplaner till specifika jobb.</td>
</tr>
<tr class="even">
<td>Jobbtyper</td>
<td>Jobbtyper används för att klassificera och filtrera kompensationsplaner till specifika jobb.</td>
</tr>
<tr class="odd">
<td>Typer av variabel kompensation</td>
<td>Variabla kompensationstyper, till exempel ersättning i aktier eller kontantbonusar, ställs in i variabla kompensationsplaner.</td>
</tr>
<tr class="even">
<td>Kompensationsrutnät</td>
<td>Kompensationsrutnät innehåller kompensationsstrukturen.  Kompensationsrutnät kan användas av en eller flera kompensationsplaner.</td>
</tr>
<tr class="odd">
<td>Resultatplaner</td>
<td>Resultatplaner används för att associera resultat med en allokeringsmatris så att du kan använda planen i en resultatlönestrategi.</td>
</tr>
<tr class="even">
<td>Resultatvärderingar</td>
<td>Resultatvärderingar används i resultatplaner när du vill fastställa beloppet för en meritbelöning eller resultatbelöning.</td>
</tr>
</tbody>
</table>

## <a name="process-events"></a>Processhändelser
En processhändelse beräknar kompensationsinformation för en angiven period för alla medarbetare som har anmälts till minst en fast eller variabel kompensationsplan. Du kan köra en processhändelse flera gånger för att testa eller uppdatera beräknade kompensationsresultat.

<a name="compensation-events"></a>Kompensationshändelser
-------------------

Varje gång en processhändelse körs skapas en kompensationshändelse.  Händelser för medarbetarkompensation innehåller resultaten av kompensationsprocessen för varje anställd som omfattas av den processhändelsen.  När beräkningarna är korrekta kan du ladda kompensationshändelsen för att uppdatera kompensationsposterna för de medarbetare som påverkas av processhändelsen.

## <a name="recommendations"></a> Rekommendationer
När du har kört en processhändelse kan du rekommendera justeringar av en medarbetares meritökning eller belöningsbelopp baserat på de beräknade riktlinjerna för processhändelsen. Om du vill göra rekommendationer för medarbetare måste du aktivera rekommendationer när du ställer in kompensationsplaner eller när du ställer in processhändelsen.




