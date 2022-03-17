---
title: Frisläpp till distributionslager
description: Det här ämnet innehåller information om processen frisläppning till lagerställe. I artikeln beskrivs entiteter som skapas när du frisläpper en order till lagerställe och vilka alternativ du kan använda när du startar processen.
author: mirzaab
ms.date: 8/13/2021
ms.topic: article
ms.search.form: WHSReleaseToWarehouse, WHSReleaseToWarehouseSalesOrder, WHSReleaseToWarehouseTransferOrder, WHSLoadPlanningWorkbench, WHSWaveTemplateTable, WHSWorkTemplateTable, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3269bf3f8a5475fb85e6b51514db29006be9aab1
ms.sourcegitcommit: b52ff5dfd32580121f74a5f262e5c2495e39d578
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376218"
---
# <a name="release-to-warehouse"></a>Frisläpp till distributionslager

[!include [banner](../../includes/banner.md)]

Det här ämnet innehåller information om processen frisläppning till lagerställe. I artikeln beskrivs entiteter som skapas när du frisläpper en order till lagerställe och vilka alternativ du kan använda när du startar processen.

## <a name="release-to-warehouse-overview"></a>Översikt över frisläppning till lagerställe

Frisläppning till lagerställe är processen att göra lagret klart för bearbetning av utförsel. När du frisläpper en order till lagerstället skapas lastrader och leveranser. Om automatisk påfyllnadsbearbetning har konfigurerats, skapas även laster och obligatoriskt arbete. Konfigurationen av de entiteter som ingår beror på systeminställningarna. Det här avsnittet i ämnet granskar de entiteter som skapas under frisläppningen till lagerställe och de systeminställningar som definierar dem.

En *leverans* är en grupp av försäljningsorder- eller överföringsorderrader för samma kund eller samma leveransadress.

En *last* är en grupp av försäljningsorder- eller överföringsorderrader som är grupperade tillsammans och som vanligtvis förs ut på en enda lastbil, tågvagn eller annat transportsätt. En last kan ha en eller flera leveranser. Du kan skapa en last manuellt genom att lägga till orderrader i en ny last. I det här fallet tilldelas orderrader lasten innan frisläppningen till lagerstället initieras, och de kan bara frisläppas från sidan **Workbench för lastplanering**.

Lagerställe *arbete* är alla lagerställeåtgärder som utförs av en lagerarbetare. Vanligtvis består lagerställearbeten av minst två på varandra följande åtgärder: en lagerarbetare plockar upp lagerbehållningen på en plats och för sedan in den på en annan plats.

När order frisläpps till lagerstället skapar systemet *lastrader* och grupperar dem till leveranser. Leveranskonsolideringsprocessen gör det möjligt att konsolidera leveranser automatiskt under frisläppningen till lagerställe. Mer information finns i [Policyer för leveranskonsolidering](about-shipment-consolidation-policies.md).

Systemet använder *påfyllnader* för att skapa plockarbete och laster för leverans. En *påfyllnadsmall* måste vara tillgänglig för den typ av påfyllnad som du vill skapa och för orderradens lagerställe. Påfyllnadsmallar för typen *Leverans* används för att leverera artiklar för försäljningsorder och överföringsorder.

Varje påfyllnadsmall innehåller *påfyllnadsmetoder*. Med påfyllnadsmetoder kan du utföra åtgärder som exempelvis att skapa arbete för påfyllnaden eller skapa laster. Påfyllnadsmallen för leveranspåfyllnader kan till exempel innehålla metoder för att skapa laster, allokera rader till påfyllnader, lagerpåfyllnad och skapa plockningsarbete för påfyllnaden. Påfyllnadsmallen skapar inställningar som definierar hur påfyllnaden ska genereras och bearbetas, vilka steg som måste utföras manuellt och vilka steg som utförs automatiskt. Mer information finns i [Påfyllnadsmallar](wave-templates.md). Beroende på konfigurationen för din påfyllnadsmall skapas därför antingen en påfyllnad automatiskt, bearbetas och frisläpps när du frisläpper en order till lagerställe, eller så utförs en del av eller alla dessa åtgärder manuellt efter att frisläppning till lagerställe har gjorts.

När en påfyllnad bearbetas skapar systemet plockningsarbete, baserat på lämplig *arbetsmall* och *platsdirektiv*, och gör det arbetet tillgängligt på mobila enheter. Arbetsmallen bestämmer hur arbetet utförs för varje lagerställeprocess, och platsdirektivet anger plock- och införselplatser för lagerrörelse. Mer information finns i [Lagerpåfyllnad och Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv](control-warehouse-location-directives.md).

> [!NOTE]
> Som standard bearbetas påfyllnader i batchläge.

Under en påfyllnadsbearbetning skapar systemet vanligtvis en ny beläggning för varje försändelse som ingen last tilldelas till. Om du vill att ej tilldelade leveranser ska tilldelas befintliga leveranser i stället, kan du använda den avancerade byggfunktionen för påfyllnadslaster. Mer information finns i [Avancerad lastuppbyggnad under påfyllnad](advanced-load-building-during-wave.md) .

På sidorna **Försäljningsorder** och **Överföringsorder** kan du granska de entiteter som skapas för orderrader under frisläppningen till lagerställe.

- Sidan **Försäljningsorder**:

    - På snabbfliken **Försäljningsorderrader** väljer du **Lagerställe** och på menyn väljer du sedan **Leveransinformation** för att öppna relaterade leveranser, **Lastinformation** för att öppna relaterade laster och **Information om arbete** för att öppna information om relaterat arbete.
    - På snabbfliken **Radinformation** väljer du fliken **Last** för att visa relaterade laster.

- Sidan **Överföringsorder**:

    - På fliken **Leverera** i åtgärdsrutan väljer du **Leveransinformation** för att öppna relaterade leveranser eller **Lastinformation** för att öppna relaterade laster.
    - På snabbfliken **Överföringsorderrader** väljer du **Information om arbete** för att öppna information om relaterat arbete.

Slutsatsen är att när en order frisläpps till lagerstället fungerar det mest automatiserade flödet på följande sätt:

1. Systemet skapar en leverans för ordern och en påfyllnad.
1. Påfyllnaden bearbetas.
1. Systemet skapar en last och ett arbets-ID.

Beroende på lastmallar, arbetsmallar och inställningar för platsdirektiv kan vissa steg i flödet bli manuella. Generellt sett förblir flödet dock detsamma.

Du har flera alternativ för hur du frisläpper en order till lagerstället. Du kan utföra åtgärden manuellt eller konfigurera ett batchjobb. Resten av avsnitten i den här ämnesöversikten innehåller information om hur du kan utföra en frisläppning för lagerställe.

## <a name="manual-release-to-the-warehouse-from-the-sales-orders-and-transfer-orders-pages"></a>Manuell frisläppning till lagerstället från sidorna Försäljningsorder och Överföringsorder

Du kan frisläppa en order till lagerstället direkt från sidan **Försäljningsorder** eller sidan **Överföringsorder** genom att välja **Frisläpp till lagerställe**.

- På sidan **Försäljningsorder** finns knappen på fliken **Lagerställe** i åtgärdsrutan.
- På sidan **Överföringsorder** finns knappen på fliken **Leverera** i åtgärdsrutan.

Från sidan **Försäljningsorder** kan du frisläppa flera försäljningsorder samtidigt.

## <a name="manual-release-to-the-warehouse-from-the-release-to-warehouse-pages"></a>Manuell frisläppning till lagerstället från sidorna Frisläpp till lagerställe

Systemet innehåller för närvarande tre sidor där du kan granska rader för flera order och frisläppa dem till lagerstället:

- **Släpp till lagerställe** (**Lagerstyrning \> Släpp till lagerställe \> Släpp till lagerställe**) – På den här sidan kan du arbeta med både försäljningsorder och överföringsorder. Den ger dock lägre prestanda än de två andra sidorna. Denna sida kommer snart att bli inaktuell.
- **Släpp försäljningsorder till lagerställe** (**Lagerstyrning \> Släpp till lagerställe \> Släpp försäljningsorder till lagerställe**) – På den här sidan kan du bara arbeta med försäljningsorder. Den ger dock bättre prestanda än sidan **Släpp till lagerställe**.
- **Släpp överföringsorder till lagerställe** (**Lagerstyrning \> Släpp till lagerställe \> Släpp överföringsorder till lagerställe**) – På den här sidan kan du bara arbeta med överföringsorder. Den ger dock bättre prestanda än sidan **Släpp till lagerställe**.

Alla tre sidor har liknande funktionalitet, vilket beskrivs i resten av det här avsnittet. Alla låter dig välja orderrader eller hela order och sedan frisläppa dem till lagerstället.

Var och en av sidorna består av en övre del där du kan välja orderrader och en nedre del, där du kan initiera frisläppningen till lagerställeprocessen. Du kan använda filter i den övre delen om du vill söka efter de försäljningsorderrader du vill frisläppa. Sidan **Släpp till lagerställe** har en separat flik för försäljningsorder och överföringsorder i den övre delen, medan de två andra sidorna bara visar en typ av order.

Verktygsfältet i den övre delen har följande knappar som du använder för att välja orderrader som ska frisläppas till lagerstället:

- **Lägg till** – Välj en eller flera orderrader i den övre delen och välj sedan den här knappen till dessa rader i den nedre delen.
- **Lägg till alla** – Lägg till alla rader från den övre delen i den nedre delen.
- **Lägg till order** – Välj en order och välj den här knappen om du vill lägga till alla rader från den ordern i den nedre delen.

När du är klar med att lägga till rader i den nedre delen markerar du varje rad som du vill frisläppa. Välj sedan **Släpp till lagerställe** i verktygsfältet för att frisläppa raderna till lagerstället.

## <a name="manual-release-to-the-warehouse-from-the-load-planning-workbench-page"></a>Manuell frisläppning till lagerstället från sidan Workbench för lastplanering

Du kan också manuellt frisläppa order till lagerstället genom att använda sidan **Workbench för lastplanering**. På den här sidan kan du ordna orderrader i laster och sedan frisläppa dem till lagerstället.

För att öppna sidan **Workbench för lastplanering** går du till **Lagerstyrning \> Laster**. Du kan också öppna den från sidorna **Försäljningsorder** och **Överföringsorder**. I den övre delen av sidan kan du välja försäljningsorderrader på fliken **Försäljningsrader** och överföringsorderrader på fliken **Överföringsrader**, och sedan lägga till dessa rader till en ny eller befintlig last.

Fliken **Tillgång och efterfrågan** i åtgärdsfönstret innehåller följande knappar som du kan använda för att lägga till orderrader i den övre delen till en last:

- **Till ny last** – Välj en eller flera orderrader i den övre delen och välj sedan den här knappen för att skapa en ny last och lägga till dessa rader i den.
- **Till befintlig last** – Välj en eller flera orderrader i den övre delen och välj sedan den här knappen för lägga till dessa rader i en befintlig last.
- **Hel order till ny last** – Välj order och välj sedan den här knappen för att skapa en ny last och lägga till alla rader från dessa order i den.
- **Hel order till befintlig last** – Välj en order och välj sedan den här knappen för att lägga till alla rader från denna order i en befintlig last.

I den nedre delen kan du granska de laster som har skapats. För att släppa laster till lagerstället, välj lasterna och välj **Släpp \> Släpp till lagerställe** på verktygsfältet. Om du använder automatisk påfyllnadsbearbetning skapas leveranser och arbets-ID:n när frisläppningen till lagerställeåtgärden utförs. Det beror på att laster redan har tilldelats orderrader.

## <a name="automatic-release-to-the-warehouse"></a>Automatiskt släpp till lagerställe

Om du vill släppa order automatiskt till lagerstället använder du jobben **Automatisk frisläppning av försäljningsorder** och **Automatisk frisläppning av överföringsorder**.

Följ stegen nedan för att konfigurera batchjobbet som släpper försäljningsorder:

1. Gå till **Lagerstyrning \> Släpp till lagerställe \> Automatiskt släpp av försäljningsorder**.
1. I dialogrutan **Automatisk frisläppning av försäljningsorder**, på snabbfliken **Parametrar**, anger du följande fält:

    - **Kvantitet att frisläppa** – Välj om hela kvantiteten eller endast den fysiskt reserverade kvantiteten ska släppas till lagerstället.
    - **Tillåt frisläppning av delvis frisläppta order** – Ange om återstående kvantiteter för delvis frisläppta order ska frisläppas till lagerstället.
    - **Behåll reservationer vid fel vid frisläppning** – Ange om kvantiteter som automatiskt reserverats för en försäljningsorder ska förbli reserverade om frisläppningen till lagerstället misslyckas.
    - **Gruppversioner efter kund** – Ange huruvida systemet ska bearbeta frisläppning till distributionslager separat för varje kund eller om det ska frisläppa alla försäljningsorder samtidigt. När detta alternativ anges som *Ja* samlar systemet in alla försäljningsorderrader för en vald kund, frisläpper dessa order till lagerstället och bearbetar sedan nästa kund. När detta alternativ är inställt på *Nej* kommer systemet att frisläppa alla tillgängliga försäljningsorderrader i en enda version till distributionslagret. Genom att aktivera detta alternativ förbättras prestanda och effektivitet i frisläppningen till lagerställebearbetningen. Du måste dock vara försiktig när du använder det här alternativet tillsammans med cykelmallar som är konfigurerade att bearbeta cykler vid frisläppning till lagerställe, detta eftersom denna kombination kan komma att generera många cykler för individuella kunder som alla genererar arbete för endast denna kund. Om du vill generera arbete som kombinerar försändelser för flera kunder, ska du antingen stänga av alternativet *Gruppera frisläppningar efter kund* eller konfigurera cykelmallarna så att dessa använder senareläggning av bearbetningen.
    - **Låst orderhantering** – Välj hur systemet ska hantera försäljningsorder som för tillfället är låsta på grund av att de redigeras av andra användare eller processer:

        - *Vänta tills order låses upp* – Systemet ska vänta tills order blir olåsta innan de frisläpps till lagerstället. I det här fallet kan frisläppningen till lagerstället ta längre tid.
        - *Hoppa över låsta order* – Systemet ska hoppa över låsta order.

    - **Giltiga ordertyper** – Välj de typer av försäljningsorder som ska inkluderas i batchen.
    - **Kreditgränstyp** – Välj om kreditgränskontroller ska göras under frisläppningen till lagerstället och, om checkarna ska utföras, den transaktionsinformation som ska ingå i dem.

1. Välj **Filter** på snabbfliken **Poster som ska ingå** för att styra vilka order som ska bearbetas. En standarddialogruta för fråga visas där du kan definiera urvalskriterier, sorteringskriterier och sammankopplingar. Fälten fungerar precis som för andra typer av frågor i Microsoft Dynamics 365 Supply Chain Management.
1. På snabbfliken **Kör i bakgrunden** väljer du om jobbet ska köras i batchläge och/eller konfigurerar ett återkommande schema. Fälten fungerar precis som för andra typer av [bakgrundsjobb](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.
1. Välj **OK** för att använda dina inställningar och initiera frisläppningen till lagerstället.

Följ stegen nedan för att konfigurera batchjobbet som släpper överföringsorder:

1. Gå till **Lagerstyrning \> Släpp till lagerställe \> Automatiskt släpp av transferorder**.
1. I dialogrutan **Automatisk frisläppning av överföringsorder**, på snabbfliken **Parametrar**, anger du följande fält:

    - **Kvantitet att frisläppa** – Välj om hela kvantiteten eller endast den fysiskt reserverade kvantiteten ska släppas till lagerstället.
    - **Tillåt frisläppning av delvis frisläppta order** – Ange om återstående kvantiteter för delvis frisläppta order ska frisläppas till lagerstället.
    - **Gruppera frisläppningar per destinationslagerställe** – Ange om systemet ska släppa alla överföringsorder samtidigt, eller om det ska gruppera överföringsorderrader efter destinationslagerställe och sedan släppa varje grupp till lagerstället separat.

1. Välj **Filter** på snabbfliken **Poster som ska ingå** för att styra vilka order som ska bearbetas. En standarddialogruta för fråga visas där du kan definiera urvalskriterier, sorteringskriterier och sammankopplingar. Fälten fungerar precis som de fungerar för andra typer av frågor i Supply Chain Management.
1. På snabbfliken **Kör i bakgrunden** väljer du om jobbet ska köras i batchläge och/eller konfigurerar ett schema för upprepning. Fälten fungerar precis som för andra typer av [bakgrundsjobb](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.
1. Välj **OK** för att använda dina inställningar och initiera frisläppningen till lagerstället.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
