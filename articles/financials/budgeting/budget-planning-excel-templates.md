---
title: "Budgetplaneringsmallar för Excel"
description: "Det här avsnittet beskriver hur du skapar Microsoft Excel-mallar som kan användas med budgetplaner."
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 156688b705337331e083ebc19fded57b028acb67
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="budget-planning-templates-for-excel"></a>Budgetplaneringsmallar för Excel

[!INCLUDE [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du skapar Microsoft Excel-mallar som kan användas med budgetplaner.

Det här avsnittet beskriver hur du skapar Excel-mallar som ska användas med budgetplaner som använder vanlig demodatauppsättning och administratörsinloggning. Mer information om budgetplanering finns [Översikt för budgetplanering.](budget-planning-overview-configuration.md) Du kan även följa guiden [Budgetplanering 101](budget-plan.md) för att lära dig grundläggande modulkonfiguration och användning.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Skapa ett kalkylblad med en dokumentlayout för budgetplan

Budgetplandokument kan visas och redigeras med hjälp av en eller flera av layouter. Varje layout kan ha en associerad budgetplansmall som låter dig visa och redigera budgetplandata i ett Excel-kalkylblad. I det här avsnittet genereras en budgetplansmall med hjälp av en befintlig layoutkonfiguration. 

1. Öppna **Budgetplanlista** (**Budgetering** &gt; **Budgetplaner**). 
2. Klicka på **Ny** om du vill skapa en ny budgetplan. 

   [![Budgetplanslista](./media/bpt11-1024x552.png)](./media/bpt11.png) 

3. Använd radalternativet **Lägg till** för att lägga till rader. Klicka på **Layout** för att visa dokumentlayoutens konfiguration för budgetplanen. 

   [![Lägg till budgetplaner](./media/bpt2-1024x274.png)](./media/bpt2.png) 

Du kan granska layoutkonfigurationen och justera den efter behov. 
1. Navigera till **Mall** &gt; **Generera** för att skapa en Excel-fil för den här layouten. 
2. När mallen har skapats går du till **Mall** &gt; **Visa** om du vill öppna och granska mallen för budgetplan. Du kan spara Excel-filen på hårddisken. 

[![Spara som](./media/bpt3-1024x545.png)](./media/bpt3.png)

> [!NOTE] 
> Budgetplanens dokumentlayout kan inte redigeras sedan en Excel-mall har associerats med den. För att ändra layouten, ta bort associerad Excel-mallfil och återskapa den. Detta krävs för att hålla fälten i layouten och kalkylbladet synkroniserade. 

Excel-mallen innehåller alla element från budgetplanens dokumentlayout, där kolumnen **Tillgängliga i kalkylbladet** har angetts som True. Överlappande element tillåts inte i Excel-mallen. Om layouten exempelvis innehåller kolumner för Begäran K1, Begäran K2, Begäran K3 och Begäran K4 och en kolumn för total begäran som motsvarar summan för alla 4 kvartalkolumner, är endast den kvartalsvisa kolumnen (totalkolumnen) tillgänglig att användas i Excel-mallen. Excel-filen kan inte uppdatera överlappande kolumner under uppdateringen, detta eftersom informationen i tabellen kan bli för gammal eller felaktig.

[![Exempel](./media/bpt4-1024x615.png)](./media/bpt4.png)

> [!NOTE] 
> Om du vill undvika problem med att visa och redigera budgetplandata med Excel, bör samma användare vara inloggad på både Microsoft Dynamics 365 for Finance and Operations och Office-tillägget för datakoppling till Microsoft Dynamics.

## <a name="add-a-header-to-budget-plan-document-template"></a>Lägg till en sidrubrik i en dokumentmall för budgetplan
För att lägga till sidrubriksinformation, markera den översta raden i Excel-filen och infoga tomma rader. Klicka på **Design** i **Datakoppling** för att lägga till sidhuvudfält i Excel-filen.

[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png) 

I fliken **Design**, klicka på fälten **Lägg till** och markera sedan **BudgetPlanHeader** som datakälla för enheten.

[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)

Peka markören på önskad plats i Excel-filen. Klicka på knappen **Lägg till etikett** för att lägga till fältetiketten på vald plats. Välj **Lägg till värde** för att lägga till värdefältet på vald plats. Klicka på **Klart** för att stänga designverktyget.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>[![bpt7](./media/bpt7.png)](./media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Lägg till beräknad kolumn i ett dokumentmallsregister för budgetplan
--------------------------------------------------------------

Därefter kommer beräknade kolumner att läggas till i dokumentmall för budgetplan. En kolumn vid namn **Total begäran**, som sammanfattar kolumnerna Begäran K1: Begäran K4, samt en **Justering**-kolumn, som beräknar kolumnen **Total begäran** genom en fördefinierad faktor.

Klicka på **Design** i **Datakoppling** för att lägga till kolumner i registret. Klicka på **Redigera** bredvid datakällan **BudgetPlanWorksheet** om du vill börja lägga till kolumner.

[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png) 

Den valda fältgruppen visar de kolumner som finns i mallen. Klicka på **Formel** för att lägga till en ny kolumn. Namnge den nya kolumnen och klistra sedan in formeln i fältet **Formel**. Klicka på **Uppdatera** för att klistra in kolumnen.

[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> Ange formeln genom att skapa den i kalkylbladet och kopiera den sedan till fönstret **Design**. Ett register avsett för Finance and Operations namnges vanligtvis "AXTable1". För att till exempel summera Begäran K1 : Begäran K4-kolumner i kalkylbladet blir formeln = AxRegister1\[Begäran K1\]+ AxRegister1\[Begäran K2\]+ AxRegister1\[Begäran K3\]+ AxRegister1\[Begäran K4\].

Upprepa dessa steg för att infoga kolumnen **Justering**. Använd formeln = AxRegister1\[Total begäran\]\*$I$ 1 för den här kolumnen. Detta kommer ta värdet i cell I1 och multiplicera värdena i kolumnen **Total begäran** för att beräkna justeringsbeloppen.

Spara och stäng Excel-filen. Återgå till Finance and Operations. I **Layout** klickar du på **Mall &gt; Överför** för att överföra den sparade Excel-mallen som ska användas för budgetplanen. 

[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Stäng skjutreglaget **Layout**. I dokumentet **Budgetplan** klickar du på **Kalkylblad** för att visa och redigera dokumentet i Excel. Observera att den justerade Excel-mallen användes för att skapa det här budgetplanskalkylbladet, och beräknade kolumner uppdateras med hjälp av de formler som definierades i föregående steg. 

[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Tips och trick för att skapa budgetplansmallar
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Kan jag lägga till och använda ytterligare datakällor i en budgetplansmall?

Ja, du kan använda menyn **Design** för att lägga till ytterligare enheter i samma eller andra ark i Excel-mallen. Du kan till exempel lägga till datakällan **BudgetPlanProposedProject** om du vill skapa och underhålla en lista över föreslagna projekt samtidigt som du arbetar med budgetplandata i Excel. Observera att bland annat omfattande datakällor kan påverka prestandan i Excel-arbetsboken. 

Du kan använda alternativet **Filter** **Datakoppling** för att lägga till önskade filter bland ytterligare datakällor.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Kan jag dölja alternativet Design i datakopplingen för andra användare?

Ja, öppna alternativet **Datakoppling** för att dölja alternativet **Design** från andra användare.

[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)

Expandera **Alternativ för datakoppling** och rensa kryssrutan **Aktivera design**. Detta döljer alternativet **Design** från **Datakoppling**.

[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Kan jag förhindra att användare av misstag stänger datakopplingen när de arbetar med data?

Vi rekommenderar att låsa mallen om du vill hindra användare från att stänga den. Om du vill aktivera låset klickar du på **Datakoppling**; en pil visas längst upp i det högra hörnet. 

[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Klicka på pilen för att visa en ytterligare meny. Välj **Lås**.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Kan jag använda andra Excel-funktioner som cellformatering, färger, villkorsstyrd formatering och diagram med mina budgetplansmallar?

Ja, de flesta vanliga Excel-funktioner fungerar i budgetplansmallar. Vi rekommenderar att använda färgkodning så att användare kan skilja mellan skrivskyddade och redigerbara kolumner. Villkorsstyrd formatering kan användas för att framhäva vissa problematiska delar av budgeten. Totalsummor för kolumner kan enkelt visas med vanliga Excel-formler ovanför tabellen.

Du kan också skapa och använda pivottabeller och diagram för ytterligare grupper och visualiseringar av budgetdata. På fliken **Data**, i gruppen **Anslutningar**, klickar du på **Uppdatera alla** och sedan på **Anslutningsegenskaper**. Klicka på fliken **Användning**. Under fliken **Uppdatera** markerar du kryssrutan **Uppdatera data när filen öppnas**. 

[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)




