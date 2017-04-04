---
title: Elimineringsregler
description: "Det här avsnittet innehåller information om elimineringsregler och de olika alternativen för rapportering om elimineringar."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: db4b05bc55d735513d7580ca5908a1e84eb760c6
ms.openlocfilehash: 152b63fdfc78b3c4e79b93340d18c5cf69257024
ms.lasthandoff: 03/31/2017


---

# <a name="elimination-rules"></a>Elimineringsregler

Det här avsnittet innehåller information om elimineringsregler och de olika alternativen för rapportering om elimineringar.

Elimineringstransaktioner behövs när en överordnad juridisk person gör affärer med en eller flera underordnade juridiska personer och använder konsoliderad ekonomisk rapportering. Konsoliderade bokslut måste innehålla transaktioner som uppstår mellan den konsoliderade organisationen och andra enheter utanför den organisation. Därför måste transaktioner mellan juridiska personer som tillhör samma organisation vara bort, eller elimineras så att de inte visas i finansiella rapporter från redovisningen. Det finns flera sätt att rapportera om elimineringar:

-   En elimineringsregel kan skapas och bearbetas i ett konsoliderings- eller elimineringsföretag.
-   Den ekonomiska rapporteringen kan användas för att visa elimineringskontona och dimensionerna i en specifik rad eller kolumn.
-   En separat juridisk person kan användas till att bokföra manuella transaktionsposter för att spåra elimineringar.

Det här avsnittet beskriver elimineringsregler som bearbetas i ett konsolidering- eller elimineringsföretag. Du ställer in elimineringsregler när du vill skapa elimineringstransaktioner i en juridisk person som anges som destination för elimineringar. Den juridiska personen på destinationen kallas för eliminerande juridisk person. Elimineringsjournaler kan skapas antingen under konsolideringen eller med hjälp av ett elimineringsjournalförslag. Innan du ställer in elimineringsregler bör du känna till följande termer:

-   **Juridisk person, källa** – Den juridiska person där beloppen som elimineras bokfördes.
-   **Destinationens juridiska person** – Den juridiska personen där elimineringsreglerna registreras.
-   **Juridisk person för eliminering** – Den juridiska person som anges som destination för elimineringar.
-   **Konsoliderad juridisk person** – Den juridiska person som skapas för att rapportera ekonomiska resultat för en grupp juridiska personer. De ekonomiska data från de juridiska personerna konsolideras i den här juridiska personen, och sedan skapas en ekonomisk rapport med hjälp av dessa kombinerade data.

Följande tabell visar de transaktionstyper som kanske måste elimineras.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>transaktionstyp</th>
<th>Exempel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Försäljningsorderregistrering och fakturering (centraliserad bearbetning)</td>
<td>Du säljer en produkt till en kund på uppdrag av en annan juridisk person i din organisation.</td>
</tr>
<tr class="even">
<td>Försäljningsorderregistrering (koncernintern/företagsintern) och fakturering</td>
<td>Du säljer produkter mellan juridiska personer i din organisation.</td>
</tr>
<tr class="odd">
<td>Inköpsorder (centraliserad bearbetning)</td>
<td>Du kan köpa lager, varor, tjänster, anläggningstillgångar och andra produkter från en leverantör på uppdrag av en annan juridisk person i din organisation.</td>
</tr>
<tr class="even">
<td>Lagerhantering (koncernintern/företagsintern)</td>
<td><ul>
<li>Du överför en juridisk persons lager till anläggningstillgångar för en annan juridisk person i din organisation.</li>
<li>Du överför en juridisk persons lager till lagret för en annan juridisk person i din organisation.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Lagerspårning under transport</td>
<td>Du överför artiklar mellan lagerställen inom samma juridiska person, men mellan olika geografiska platser.</td>
</tr>
<tr class="even">
<td>Centraliserad fakturabearbetning i leverantörsreskontra</td>
<td>Du kan registrera en faktura på uppdrag av en annan juridisk person i din organisation.</td>
</tr>
<tr class="odd">
<td>Centraliserad betalningsbearbetning i leverantörsreskontra</td>
<td>Du kan betala en faktura på uppdrag av en annan juridisk person i din organisation.</td>
</tr>
<tr class="even">
<td>Kassahantering (centraliserad hantering)</td>
<td><ul>
<li>Du kan bearbeta skattebetalningar, återbetalningar av skatt, ränteavgifter, lån, förskott, betalda utdelningar och förutbetalda royalties eller provisioner.</li>
<li>Du kan betala en utgift på uppdrag av en annan juridisk person i din organisation. Fakturan anges i den juridiska målpersonens böcker och du måste göra kvittningar mellan olika juridiska personer. En juridisk person betalar till exempel utgiftsrapporten för en medarbetare i en annan juridisk person. I det här fallet har medarbetarens utgiftsrapport som är relaterade till en annan juridisk person.</li>
<li>Du överför medel från en juridisk person till en annan i din organisation.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Kundreskontra (centraliserad hantering)</td>
<td>Du tar emot kontanter för en annan juridisk persons kundfaktura och du sätter in checken på den juridiska personens bankkonto.</td>
</tr>
<tr class="even">
<td>Lön (centraliserad hantering, koncernintern/företagsintern)</td>
<td><ul>
<li>Du kan betala en annan juridisk persons Lön. En juridisk person kanske till exempel betalar sina egna löner till de anställda, men debiterar tillbaka arbete som en medarbetare har utfört för en annan juridisk person under lönekörningen. Eller om en medarbetare har arbetat halvtid för den juridiska personen A och halvtid för den juridiska personen B och förmånerna gäller för hela lönen. I så fall innehåller medarbetarens lön betalningen från båda juridiska personer. Det är inte bara löner som bokförs utan även skatter, förmåner, avdrag och periodiseringar för löner bokförs.</li>
<li>Du överför arbete från en avdelning eller division till en annan.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Anläggningstillgångar (koncernintern/företagsintern)</td>
<td>Du överför anläggningstillgångar till en annan juridisk persons anläggningstillgångar eller lager.</td>
</tr>
<tr class="even">
<td>Allokeringar (koncernintern/företagsintern)</td>
<td>Du kan bearbeta företagsallokeringar. Allokeringar är aktiviteter för alla konton som är allokerade, oavsett den ursprungliga modulen.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>Exempel
Din juridiska person, juridisk person A, säljer prylar till en annan juridisk person inom din organisation, juridisk person B. Följande exempel visar hur transaktionerna som uppstår mellan de två juridiska personerna kanske måste elimineras:

-   Juridisk person A säljer en pryl som kostar 10,00 till juridisk person B för 10,00.
-   Juridisk person A säljer en pryl som kostar 10,00 till juridisk person B för 10,00 plus 2,00 i faktiska fraktkostnader.
-   Juridisk person A säljer en pryl som kostar 10,00 till juridisk person B för 15,00 och tillerkänns en marginal på försäljningen.
-   Juridisk person A säljer en pryl som kostar 10,00 till juridisk person B för 15,00 och tillerkänns halva marginalen på försäljningen. Juridisk person B tillerkänns den andra halvan av marginalen på försäljningen. Därför delas intäkten. Delade intäkter ger ett incitament till order från en annan juridisk person i organisationen i stället för en extern organisation.

Alla dessa transaktioner skapar koncerninterna transaktioner som bokförs på förfaller till- och förfaller från-konton. Dessutom kan dessa transaktioner kanske omfatta påläggs- och nedsättningsbelopp när beloppet för den koncerninterna försäljningen inte är lika med kostnaden för de varor som sålts.

## <a name="set-up-elimination-rules"></a>Ställ in elimineringsregler
När du ställer in elimineringsregler i Dynamics 365 för operationer rekommenderar vi att du skapar en ekonomisk dimension som särskilt avser eliminering. De flesta kunder kalla den handel Partner eller något liknande. Om du inte vill använda en ekonomisk dimension kan vara ha huvudkonton som gäller endast för koncerninterna transaktioner. 

Inställningar för elimineringar finns i området Inställningar i modulen konsolideringar. När du anger en beskrivning av regeln, måste du välja det företag elimineringsjournalen bokförs till. Detta bör vara ett företag som **Använd för ekonomisk elimineringsprocess** markerat juridisk person. 

Du kan ange ett datum då elimineringsregeln träder i kraft, och när det har gått ut, om det behövs. Du måste ange **aktiva** till **Ja** om du vill att den ska vara tillgänglig i förslagsprocessen eliminering. Välj ett journalnamn som har ett slags **eliminering**.

Du kan definiera regler för produkterna faktiskt bearbetas genom att klicka på när du har definierat grunderna **rader**. Det finns två olika elimineringar eliminerar beloppet Nettoförändring eller definiera ett fast belopp. 

Markera kontot hos din källa. Du kan använda en asterisk (\*) som jokertecken. Till exempel 1\* markerar alla konton som börjar med 1 som en datakälla för allokeringen. 

När du har valt källa konton, den **konto specifikationen** anger kontot för destinationsföretaget som används. Välj **källa** om du vill använda samma huvudkonto som definieras i den **källa** konto. Om du väljer **användardefinierade**, måste du ange ett destinationskonto. 

Specifikationen av fungerar på samma sätt. Om du väljer **källa**, används samma dimensioner i destinationsföretaget som företaget. Om du väljer **användardefinierade**, behöver du ange dimensioner i destinationsföretaget genom att klicka på den **måldimensioner** menyobjekt. 

Välj källdimensionerna och ekonomiska dimensioner och värden som används som källa för eliminering.

## <a name="process-elimination-transactions"></a>Bearbeta elimineringstransaktioner
Det finns två sätt att bearbeta elimineringstransaktioner när konsolidera online, eller skapa en journal för redovisningseliminering och köra förslagsprocessen eliminering. I det här avsnittet är avsett för skapa journalen och kör elimineringsprocessen. 

I ett företag definieras som en elimineringsföretaget Välj **elimineringsjournalen** i modulen konsolideringar. När du har valt journalnamnet, klickar du på **rader**. Du kan köra förslaget genom att välja den **förslag** -menyn och sedan välja **Elimineringsförslag**.

Välj det företag som utgör grunden för konsoliderade data och klicka på den regel som du vill bearbeta. Ange ett startdatum för att börja sökningen efter eliminering belopp och ett slutdatum för att avsluta sökdatum för eliminering. Den **bokföringsdatum GL** är det datum som används för att bokföra journalen i redovisningen. När du klickar på **OK**, kan du granska belopp och bokför journalen.


