---
title: "Budgetplaneringsmallarna för Excel"
description: "Det här avsnittet beskrivs hur du skapar en Microsoft Excel-mallar som kan användas med budgetplaner."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 0e2eb6e7c130f03edbf60a185d397d94b5d61d7d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-templates-for-excel"></a>Budgetplaneringsmallarna för Excel

Det här avsnittet beskrivs hur du skapar en Microsoft Excel-mallar som kan användas med budgetplaner.

Det här avsnittet beskrivs hur du skapar Excel-mallar som ska användas med standard demo datauppsättningen och användarinloggning Admin budgetplaner. Mer information om budgetplanering finns [översikt för budgetplaneringsprocessen.](budget-planning-overview-configuration.md) Du kan även följa de [budgetplanering 101](budget-plan.md) självstudier för att lära sig basmodulen konfigurations- och principer.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Skapa ett formulär med hjälp av budgeten planen dokumentlayout
Budgetplandokument kan visas och redigeras med hjälp av en eller flera av layouter. Varje layout kan ha en associerad dokumentet budgetplansmall att visa och redigera planen budgetdata i ett Excel-kalkylblad. I det här avsnittet genereras dokumentet en budgetplansmall använder en befintlig konfiguration av layout. Öppna den **Budget planer lista** (**budget**&gt;**budgetplaner**). Klicka på **New** du skapar en ny budgetplandokument. [![bpt1](./media/bpt11-1024x552.png)](./media/bpt11.png) 

Använd den **Lägg** rad alternativet att lägga till rader. Klicka på **layout** visa budgeten planen dokumentkonfigurationen layout. 
[![bpt2](./media/bpt2-1024x274.png)](./media/bpt2.png) 

Du kan granska konfigurationen layout och justera den efter behov. Gå till **mall**&gt;**generera** skapa en Excel-fil för den här layouten. När mallen skapas, går du till **mall**&gt;**visa** om du vill öppna och granska dokument budgetplansmall. Du kan spara filen på hårddisken. [![bpt3](./media/bpt3-1024x545.png)](./media/bpt3.png) 

> [!NOTE] 
> Budget planen dokumentets layout kan inte redigeras när en Excel-mall som är associerad med den. Ändra layouten, ta bort associerade Excel-mallfil och återskapa den. Det krävs att fälten i layouten och kalkylbladet synkroniseras. 

Excel-mallen innehåller alla element från budgeten planen dokumentets layout där de **tillgängliga i kalkylbladet** kolumn har angetts till True. Överlappande element tillåts inte i Excel-mall. Om layouten innehåller begäran K1, k2 begäran, begäran Q3 och Q4 begäran kolumner och totala begäran den här kolumnen motsvarar summan av alla kolumner för 4 kvartal, är den kvartalsvisa kolumner eller totalt exempelvis tillgängliga att användas i Excel-mall. Filen kan inte uppdatera överlappande kolumner under uppdateringen eftersom informationen i tabellen kan bli för gammal eller felaktig.

[![bpt4](./media/bpt4-1024x615.png)](./media/bpt4.png)

> [!NOTE] 
> Om du vill undvika problem med att visa och redigera planen budgetdata med Excel vara samma användare inloggad på båda Dynamics 365 för operationer och tillägget Microsoft Dynamics Office-dataanslutning.

## <a name="add-a-header-to-budget-plan-document-template"></a>Lägga till en rubrik i budgetplansmallen dokument
Lägga till rubrikinformation, markera den översta raden i filen och infoga tomma rader. Klicka på **Design** i den **dataanslutning** att lägga till huvudfält Excel-filen.

[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png) 

I den **Design** fliken ** ** klickar du på **Lägg till** fält och markera **BudgetPlanHeader** som datakälla för enheten.

[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)

Peka markören på önskad plats i filen. Klicka på **Lägg till etiketten** till fältetiketten till den angivna platsen. Välj **lägga till värdet** att lägga till värdefältet till vald plats. Klicka på **har gjort** att stänga designverktyget.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>[![bpt7](./media/bpt7.png)](./media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Lägga till en beräknad kolumn i budgeten planen dokumentregister mall
--------------------------------------------------------------

Nästa steg är beräknade kolumner läggs till dokument skapade budgetregisterposten planmall. A **totala begäran** kolumner som sammanfattar begäran K1: begäran kvartal 4 kolumner och en **justering** kolumnen beräknas den **totala begäran** kolumn med fördefinierade faktorn.

Klicka på **Design** i den **dataanslutning** att lägga till kolumner i tabellen. Klicka på **redigera** vid **BudgetPlanWorksheet** datakälla om du vill börja lägga till kolumner.

[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png) 

Valda fältgruppen visar de kolumner som finns i mallen. Klicka på **formeln** att lägga till en ny kolumn. Namnge den nya kolumnen och sedan klistra in formeln i den **formeln** fält. Klicka på **uppdatering** om du vill infoga kolumnen.

[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> Ange formeln skapar formeln i kalkylbladet och kopiera det till den **Design** fönster. En Dynamics 365 för operationer bundna register namnges vanligtvis "AXTable1". Exempelvis summera begära K1: begära kvartal 4 kolumner i kalkylbladet formeln = AxTable1\[K1 begära\]+ AxTable1\[begära K2\]+ AxTable1\[begära Q3\]+ AxTable1\[begära Q4\].

Upprepa stegen för att infoga den **justering** kolumn. Använd formeln = AxTable1\[totala begäran\]\*$I$ 1 för den här kolumnen. Detta kommer ta värdet i cell I1 och multiplicera värden i den **totala begäran** kolumn för att beräkna justeringssummorna.

Spara och stäng filen. Återgå till Dynamics 365 för operationer och i **layout**, klickar du på **mall &gt;överför** att överföra den sparade mallen i Excel som ska användas för budgetplanen. 

[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Stäng den **layout** skjutreglaget. I **budgetplanen** dokument, klickar du på **kalkylblad** visa och redigera dokument i Excel. Observera att den justerade Excel-mallen som användes för att skapa den här Budgetplanskalkylbladet och beräknade kolumner uppdateras med hjälp av formlerna som definierats i föregående steg. 

[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Tips och trick för att skapa Budgetplansmallar
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Kan jag lägga till och använda andra datakällor till en budgetplansmall?

Ja, du kan använda den **Design** menyn om du vill lägga till ytterligare enheter i samma eller andra formatmallar i mallen i Excel. Du kan till exempel lägga till den **BudgetPlanProposedProject** datakälla om du vill skapa och underhålla en lista över föreslagna projekt samtidigt när planerar arbeta med budgeten i Excel. Observera att bland annat omfattande datakällor kan påverka prestanda i Excel-arbetsboken. 

Du kan använda den **Filter** alternativet i den **dataanslutning** att lägga till ytterligare datakällor önskat filter.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Kan jag dölja alternativet Design i dataanslutning för andra användare?

Ja, öppna det **dataanslutning** alternativ som döljer den **Design** alternativet från andra användare.

[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)

Expandera **Data connector alternativ** och tar bort den **aktiverar design** kryssrutan. Döljs de **Design** alternativet från den **dataanslutning**.

[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Kan jag förhindra användare misstag stänger kopplingen Data när du arbetar med data?

Vi rekommenderar att låsa mallen om du vill hindra användare från att stänga den. Om du vill aktivera låset klickar du på **dataanslutning**, en pil visas längst upp i det högra hörnet. 

[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Klicka på pilen för en ytterligare meny. Välj **Lås**.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Kan jag använda andra Excel-funktioner som cellformatering, färger, villkorsstyrd formatering och diagram med Mina Budgetplansmallar

Ja, kommer de flesta vanliga Excel-funktionerna fungera i Budgetplansmallar. Vi rekommenderar färgkodningen för användare för att skilja mellan kolumnerna och redigeras. Villkorsstyrd formatering kan användas för att framhäva vissa problematiska delar av budgeten. Totalsummor för kolumner kan enkelt visas med vanlig Excel-formler ovanför tabellen.

Du kan också skapa och använda pivottabeller och diagram för ytterligare grupper och visualisering av budgetdata. På den **Data** fliken den **anslutningar** grupp genom att klicka på **uppdatera alla**, och klicka sedan på **egenskaper**. Klicka på den **användning** fliken. Under **uppdatera**markerar den **uppdatera data när du öppnar filen** kryssrutan. 

[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)


