---
title: Konfigurera satser
description: Tariffer i Microsoft Dynamics 365 Human Resources definierar hur mycket arbetsgivare och medarbetare som deltar i en förmån.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f846dcd0a15424ac681dd7e6a229d9da445a54e1
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092418"
---
# <a name="configure-rates"></a>Konfigurera satser

[!include [banner](includes/preview-feature.md)]

Tariffer i Microsoft Dynamics 365 Human Resources definierar hur mycket arbetsgivare och medarbetare som deltar i en förmån. Värdet kan vara ett belopp eller en flexsaldo, beroende på din konfiguration.

Använd tariffer för att fastställa hur mycket anställda och arbetsgivare som betalar för varje förmån, baserat på flera faktorer. Täckningstariffer har giltighetsdatum så att du kan spara en historisk post med tariffer. 

## <a name="set-up-rates"></a>Ställ in tariffer

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **tariffer**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | Kurs | Ett unikt namn som identifierar förmånstarriffen. |
   | Beskrivning | En beskrivning av förmånstarriffen. |
   | Giltighet | Datum då tariffen är giltig. Det aktuella systemdatumet är standardvärdet. 
   | Förfallotid | Slutdatum för tariffen. 12/31/2154 (vilket betyder aldrig) är standardvärdet. |
   | Använd nivåer | Den nivå som ska användas för beräkning av förmånspriset. En nivå för förmånspris i en nivå eller en dubbel nivå för förmånspris på två nivåer. Ett exempel på en dubbel nivå är en nivå baserad på kön och ålder. |
   | Lönefrekvens | Den lönefrekvens som avgör hur ofta förmånspriset betalas till förmånsleverantören. Om lönefrekvensen t.ex. är månadsvis representerar förmånspriset månadskostnaden. |
   | Beräkning av lönefrekvens | Metod för beräkning av lönefrekvens: standard eller årlig. |
   | Avrundning av lönefrekvens | Metod för avrundning av priset: standard eller trunkerad. |
   | Medarbetarbelopp för ickerökare | Det belopp som en förmånsleverantör debiteras för en anställd som inte är rökare. Detta är det belopp som arbetsgivaren betalar till den förmånsleverantören och som ska baseras på lönefrekvensen för tariffinställningen. |
   | Arbetsgivarbelopp för ickerökare | Det belopp som en förmånsleverantör debiteras för en anställd som inte är rökare. Detta är det belopp som arbetsgivaren betalar till den förmånsleverantören och som ska baseras på lönefrekvensen för tariffinställningen. |
   | Medarbetarbelopp för rökare | Det belopp som en förmånsleverantör debiteras för en anställd som är rökare. Detta är det belopp som arbetsgivaren betalar till den förmånsleverantören och som ska baseras på lönefrekvensen för tariffinställningen. |
   | Arbetsgivarbelopp för rökare | Det belopp som en förmånsleverantör debiteras för en anställd som är rökare. Detta är det belopp som arbetsgivaren betalar till den förmånsleverantören och som ska baseras på lönefrekvensen för tariffinställningen. |
   | Administrativt belopp | Det administrativa belopp som en tredje parts administratör debiterar. Detta är det belopp som arbetsgivaren betalar till tredje partens administratör och som ska baseras på lönefrekvensen för tariffinställningen. |
   | Flexkreditpris | Antalet flexkrediter är förmånskostnaderna. Detta gäller endast tariffer som är för förmånsplaner som associeras med flexkreditprogram. Om du använder nivåpriser definieras flexkrediten i åtgärder > nivåpriser. |
   | Ändringens giltighetsdatum | Datumet då ändringen av förmånspriset börjar att gälla. Systemet ändrar automatiskt förmånspriset och uppdaterar alla förmånsplaner som associeras med detta pris, förutsatt att du kör en ändring av uppdateringsprocessen för prisprocessen. Du bör inte ställa in detta datum om du inte vill att systemet automatiskt ska uppdatera medarbetarnas förmånsplaner utifrån denna tariff. Detta är vanligtvis reserverat för automatisk bearbetning av prisändring. Ändringens giltighetsdatum måste infalla inom förmånspriseys giltighets- och utgångsdatum. |
   | Prisändringen har slutförts | Kryssrutan Prisändringen har slutförts kommer att markeras automatiskt efter att ändringarna av förmånens pris har slutförts med hjälp av Bearbetning av uppdaterade prisändringar. |

4. Om du vill spåra och underhålla ändringar i inställningarna för förmånsgrad **åtgärder** och välj sedan **underhåll versioner**.

5. Välj **Spara**. 

## <a name="set-up-tier-rates"></a>Ställ in nivåpriser

Du kan använda nivåpriser i din prisinställning om priset varierar beroende på olika faktorer. Du kan t.ex. konfigurera nivåer som anger att om din ålder är upp till 34,99, är beloppet för ickerökare 2. Om din ålder är upp till 39,99 är beloppet för ickerökare 3.

Du kan också använda dubbla nivåer. Om du väljer **dubbla nivåer** för värdet **använd nivåer** i formuläret **inställning av pris** kan du definiera priser baserade på två dimensioner. Du kan t.ex. konfigurera ett dubbelt nivåsystem som anger att om du är man och din ålder är upp till 34,99, är beloppet för ickerökare 2. Om du är man och din ålder är upp till 39,99 är beloppet för ickerökare 3. Om du är kvinna och din ålder är upp till 34,99 är beloppet för ickerökare 1.8. Om du är kvinna och din ålder är upp till 39,99 är beloppet för ickerökare 2.8.

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **tariffer**.

2. Välj en eller flera priser i listan, välj **åtgärder** och välj sedan **nivåpriser**.

3. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- | 
   | Beskrivning | Värdet i fältet Beskrivning kommer att användas från beskrivningen i posten för prisnivåer. Detta hjälper dig att identifiera vilken prisinställning som nivåpriserna är kopplade till. |
   | Nivåkod | Välj en nivåkod. Nivåkoder definieras i formuläret nivåkoder. I systemet visas automatiskt beskrivningen av nivåkoden i rutnätet till vänster. |
   | Nivåtyp | Anger vilket fält som ska användas som urvalskriterium för beräkningsprocessen för nivåpriser. Exempel:</br></br><ul><li>Om ålder används använder systemet medarbetarens födelsedatum under beräkningsprocessen för förmånspriset.</li><li>Om lön används använder systemet medarbetarens årliga inkomsten av förmånen under beräkningsprocessen för förmånspriset.</li><li>Om Jobbtyp används använder systemet medarbetarens aktuella aktiva befattningspost för att fastställa jobbtypen genom den jobbpost som är kopplad till befattningen.</li></ul></br></br>Nivåtyperna är ålder, lön, fysisk, kön, heltidslön, jobbtyp, kompensationsregion och nivå. | 
   | Nivå | Det värde som ska användas med nivåtypen under beräkningsprocessen av förmånspriset. Exempel:</br></br><ul><li>Om nivåtypen är ålder är detta värdet för ålder.</li><li>Om nivåtypen är lön är detta lönebeloppet.</li><li> Om nivåtypen är jobbtyp är detta jobbtypen.</li></ul></br></br>Med en nivåtyp av ålder eller lön använder systemet en stigande inställning under nivåprisvalet, vilket innebär att värdet i fältet nivå representerar den nedre gränsen för nivån. Med en nivåtyp av Jobbtyp använder systemet en exakt matchningsmetod under valet av nivåpris. |
   | Beräkningstyp | Anger hur beloppet i fältet beräkningsbelopp ska användas och vilken matematik beräkning som ska utföras vid behov. Om beräkningstypen är ett fast belopp använder systemet beloppsfälten som de är. Om beräkningstypen är per $ lönebelopp eller disponering använder systemet beräkningsbeloppet och beräkningsriktningen i sin matematiska beräkning.</br></br>Om beräkningstypen är per $ lönebelopp kommer systemet att använda följande matematiska ekvation:</br></br>Årslönen dividerat med beräkningsbeloppet (avrundat uppåt eller nedåt) gånger mängden rökare eller ickerökare för anställd eller arbetsgivare.</br></br>Om beräkningstypen är per $ försäkringsbelopp kommer systemet att använda följande matematiska ekvation:</br></br>Försäkringsbelopp dividerat med beräkningsbeloppet (avrundat uppåt eller nedåt) gånger mängden rökare eller ickerökare för anställd eller arbetsgivare.</br></br>I båda beräkningarna används beräkningsriktningen för att bestämma om den årliga förmånslönen eller försäkringsbeloppet ska avrundas genom beräkningsbeloppet upp eller ned. |
   | Beräkningsbelopp | Beloppet som ska användas under beräkningsprocessen för förmånspriset. Det här beloppet blir avgränsare under den matematiska beräkningen av nivåpriset. |
   | Beräkningsriktning | Riktningen (ökning eller minskning) som det beräknade resultatbeloppet ska avrundas till. Systemet har stöd för tre beräkningsriktningar: tom (exakt metod), öka och minska.</br></br><ul><li>Om fältet är tomt används den exakta beräkningen av lönen/försäkringsbeloppet delat med beräkningsbeloppet. Om det här värdet har en kvot används detta i beräkningen.</li><li>Om ökning kommer systemet öka matematikberäkningen för lönen/försäkringsbeloppet dividerat med beräkningsbeloppet med nästa heltal, vilket innebär att 12,25 skulle öka till 13.</li><li>Om minskning kommer systemet minska matematikberäkningen för lönen/försäkringsbeloppet dividerat med beräkningsbeloppet med aktuellt heltal, vilket innebär att 12,25 skulle minska till 12.</li></ul> |
   | Medarbetarbelopp för ickerökare | Det belopp som en förmånsleverantör debiteras för en anställd som inte är rökare. Detta är det belopp som arbetsgivaren betalar till den förmånsleverantören och som ska baseras på lönefrekvensen för tariffinställningen. |
   | Arbetsgivarbelopp för ickerökare | Det belopp som en förmånsleverantör debiteras för en anställd som inte är rökare. Detta är det belopp som arbetsgivaren betalar till den förmånsleverantören och som ska baseras på lönefrekvensen för tariffinställningen. |
   | Medarbetarbelopp för rökare | Det belopp som en förmånsleverantör debiteras för en anställd som inte är rökare. Detta är det belopp som arbetsgivaren betalar till den förmånsleverantören och som ska baseras på lönefrekvensen för tariffinställningen. |
   | Arbetsgivarbelopp för rökare | Det belopp som en förmånsleverantör debiteras för en anställd som inte är rökare. Detta är det belopp som arbetsgivaren betalar till den förmånsleverantören och som ska baseras på lönefrekvensen för tariffinställningen. |
   | Administrativt belopp | Det administrativa belopp som en tredje parts administratör debiterar. Detta är det belopp som arbetsgivaren betalar till tredje partens administratör och som ska baseras på lönefrekvensen för tariffinställningen. |
   | Flexkredit för ickerökares pris | Antalet flexkrediter för förmånspris, baserat på den beräkning som definierats för prisnivån för ickerökare. Till exempel, om beräkningstypen är "Per $ försäkringsbelopp", är beräkningsbeloppet 10,000, och flexkrediten för ickerökares pris är 6, betyder det att om en ickerökande anställd väljer 10,000 $ täckning, kommer det att kosta 6 flexkrediter. Om de väljer $ 20 000 av täckning kommer det att kosta 12 flexkrediter och så vidare. |
   | Flexkreditpris för rökare | Antalet flexkrediter för förmånspris, baserat på den beräkning som definierats för prisnivån för rökare. |

5. Välj **Spara**. 
