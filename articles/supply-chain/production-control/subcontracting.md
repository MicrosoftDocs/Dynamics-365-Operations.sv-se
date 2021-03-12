---
title: Legotillverkning
description: Det här avsnittet hjälper dig att skapa en genomgång av legotillverkning i produktionen i Dynamics 365 Supply Chain Management.
author: christophernread
manager: tfehr
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3e282e0676e53200b0993dd9cb2b52e08fe97dca
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981466"
---
# <a name="subcontracting"></a>Legotillverkning

[!include [banner](../includes/banner.md)]

Det här avsnittet hjälper dig att skapa en genomgång av legotillverkning i produktionen i Microsoft Dynamics 365 Supply Chain Management. Den första delen av det här avsnittet beskriver inställningen av data. Den andra delen tar dig igenom stegen i genomgången.

## <a name="target-audience"></a>Målgrupp

I det här avsnittet får du lära dig hur du ställer in den legotillverkning i produktionen. Du kommer att använda befintliga data i den juridiska personen HQUS för att göra grundinställningen av ett flöde för legotillverkningsaktiviteten. Demodata hos den juridiska personen HQUS inkluderar inställningsparametrar som har blivit förinställda för att ge stöd till stegen i genomgången. Trots att genomgången behandlar viktiga sårbarheter och utmaningar för olika roller kan den kompletteras av systemadministratören.

## <a name="demo-scenario"></a>Demonstrationsscenario

Avancerade högtalare tillverkas i den juridiska personen HQUS. Under tillverkningsprocessen går högtalare igenom följande tre åtgärder.

- **Förmontering** - Högtalarkabinetten monteras. Materialet för kabinetten plockas på lagerstället för material innan operationen startas.
- **Beläggning** – När högtalarkabinetten har monterats måste den beläggas. Åtgärden slutförs av en leverantör (underleverantör). Den förmonterade högtalarkabinetten levereras till underleverantören för beläggning tillsammans med två material.
- **Ytbehandling** – När den förmonterade högtalarkabinetten är belagd av underleverantören returneras den till den juridiska personen HQUS så att slutmonteringen av högtalaren kan slutföras.

Följande bild visar de tre operationerna och materialet som de använder.

![Operationerna förmontering, beläggning, ytbehandling och materialet som de förbrukar](./media/subcontract01_operations-materials.png)

## <a name="setup"></a>Konfigurera

Innan du påbörjar genomgången måste du ställa in data.

### <a name="set-up-the-finished-product"></a>Ställ in den färdiga produkten

Den här proceduren hjälper dig genom inställningarna för frisläppt produkt D8100, ”Belagd kabinett”.

1. Välj **produktinformationshantering \> produkter \> frisläppta produkter** för att öppna sidan **Information om frisläppt produkt**.
2. I snabbfilterfältet anger du **D8100** för att söka efter befintlig frisläppt produkt.

    ![Filtrering för frisläppt produkt D8100 på informationssidan för frisläppt produkt](./media/subcontract02_filtering-released-products.png)

3. I åtgärdsfönstret, på fliken **tekniker**, välj **flöde** för att öppna sidan **flöde**.

    Sidan **Flöde** visar de åtta flödesversioner för frisläppt produkt D8100. Åtta flödesversioner ska delas upp mellan fyra flöden på site 1 och 5. Flöde 000400 används för kostnadsredovisning, flöde 00041 används när beläggningsoperationen är en intern operation, och flöde 00042 används när beläggningsoperationen är en extern operation.

    ![Åtta flödesversioner på sidan Flöde](./media/subcontract03_route-page.png)

4. I det övre fönstret i rutnätet **versioner**, välj flödesversion **00042** för site **5**.
5. I det nedre fönstret på fliken **översikt**, välj operation **20** (**Cbnt CtSc**) i rutnätet.

    ![Operation 20 flödesversionen 00042 för site 5 markerad](./media/subcontract04_route-version-operation.png)

6. Välj fliken **Allmänt**.

    Lägg märke till att fältet **flödestyp** har tilldelats **leverantör**. Detta värde anger att operation 20 (Cbnt CtSc) är en legotillverkningsoperation.

    ![Fältet Flödestyp anges till Leverantör på fliken Allmänt](./media/subcontract05_general-tab.png)

7. Välj fliken **Resurskrav**.

    Funktioner används för att hitta en tillämplig resurs vid produktionsplaneringen. Observera att för operation 20 (Cbnt CtSc) krävs en resurs som har två funktioner **beläggning** och **belagd kabinett**.

    ![Kapacitet för beläggning och belagda kabinett på fliken resursbehov](./media/subcontract06_resource-requirements-tab.png)

8. Välj **tillämpliga resurser** för att öppna dialogrutan **tillämpliga resurser**.

    Tre resurser hittas som matchar operationens resursbehov. Lägg märke till att 8851 och 8852 är av typen **leverantör**.

    ![Tre tillämpliga resurser i dialogrutan tillämpliga resurser.](./media/subcontract07_applicable-resources-dialog.png)

9. Välj **OK** för att stänga dialogrutan **tillämpliga resurser** och återgå till sidan **flöde**.
10. Stäng sidan **flöde** om du vill återgå till sidan **Information om frisläppt produkt**.

    ![Sidan Information om frisläppt produkt](./media/subcontract08_released-product-details-page.png)

11. I åtgärdsfönstret, på fliken **tekniker**, välj **strukturlisteversioner** för att öppna sidan **strukturlisteversioner**.

    Sidan **strukturlisteversioner** visar fyra strukturlisteversioner för frisläppt produkt D8100. Strukturlistan 000040 används för kostnadsredovisning och planering, strukturlistan 000041 används om operationen beläggning görs inom företaget, strukturlistan och 000042 och 000043 används om beläggningsoperationen gäller legotillverkning.

    Observera att artikel S8050 är en produkt av artikeltypen **Tjänst**. Den här artikeln representerar legotillverkning.

    ![Fyra strukturlisteversioner på sidan strukturlisteversioner](./media/subcontract09_bom-versions-page.png)

12. På snabbfliken **strukturlisterader**, välj **redigera** för att öppna dialogrutan **Redigera strukturlisterad**.

    När en produktionsorder har skapats och uppskattats för frisläppt produkt D8100, genereras en inköpsorder automatiskt för artikel S8050. Denna inköpsorder ska kopplas till produktionsordern. För att inköpsorder ska skapas automatiskt måste fältet **Radtyp** ställas in på **leverantör**, och du måste välja leverantörskontot för underleverantören. I det här fallet är leverantörskontot US-801.

    Observera att strukturlisteraden är ansluten till beläggningsoperationen genom operationsnummer (i vårt exempel 20).

    ![Redigera dialogrutan Strukturlista](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a>Skapa ett lösenord för lagerarbetare

Du måste definiera ett lösenord för lagerarbetare som använder den bärbara enheten.

1. Välj **lagerstyrning \> inställningar \> arbetare** för att öppna sidan **Arbetsanvändare**.
2. På snabbfliken **användare**, markerar du raden för användaren **51**.

    ![Sidan arbetsanvändare](./media/subcontract11_work-users-page.png)

3. Välj **Återställ lösenord**.
4. I fältet **Lösenord** och **Bekräfta lösenord** ange **1**.
5. Välj **Ange lösenord**.

## <a name="step-by-step-walkthrough"></a>Stegvis genomgång

**Scenario och bakgrund**

En produktionsorder på 10 enheter skapas för produkten D8100, ”belagd kabinett”. Beläggning av kabinetter är en legotillverkningsoperation som utförs av leverantör US-801 Perfect Coating Solutions. Tillverkningsordern består av tre operationer. I den första operationen sammansätts kabinetten i förväg som en intern operation. Materialet för förmonteringen har frisläppts för plockning i råmateriallagret. När förmonteringen har slutförts skickas den förmonterade kabinetten till Perfect Coating Solutions tillsammans med två material som krävs för beläggningsoperationen. När den belagda kabinetten tas emot från säljaren går den igenom en slutlig montering på plats innan den rapporteras som färdig.

1. Välj **produktionskontroll \> produktionsorder \> alla produktionsorder** för att öppna sidan **alla produktionsorder**.
2. I åtgärdsfönstret, välj **ny produktionsorder** för att öppna dialogrutan **skapa produktionsorder**.

    ![Dialogrutan Skapa produktionsorder](./media/subcontract12_create-production-order-dialog.png)

3. I fältet **Artikelnummer**, välj **D8100**.
4. När du har valt artikelnumret visas fälten för inventeringsdimensionerna. I fältet **Färg**, välj **Chrome**.

    Ett meddelande visas som frågar om du vill infoga aktiva versioner för strukturlista och flöde.

    ![Meddelanderuta](./media/subcontract13_message-box.png)

5. Välj **Ja**. 

    I dialogrutan **skapa produktionsorder** väljs de aktiva versionerna av strukturlistan och flödet för produkten D8100 automatiskt i fälten **Strukturlistenummer** och **Flödesnummer**. I det här fallet väljs strukturlista **000040** och **000040**.
    
    > [!NOTE]
    > För både strukturlista och flöde används version 000040 för kostnadsberäkning och planering.

6. I fltet **Site**, välj **5**.
7. I fältet **Lagerställe**, välj **51**.
8. I **Strukturlistenummer** och **Flödesnummer**, ändra värdet som valdes automatiskt till **000042**.

    > [!NOTE]
    > För både strukturlistan och flödet används version 000042 för att underleverera beläggningen av kabinetten till leverantör US-801.

    ![Värdena som anges i dialogrutan Skapa produktionsorder](./media/subcontract14_create-production-order-dialog-set.png)

9. Välj **Skapa** för att skapa produktionsordern och återgå till sidan **alla produktionsorder**.

    ![Ny produktionsorder på sidan Alla produktionsorder](./media/subcontract15_new-production-order.png)

10. I åtgärdsfönstret, på fliken **produktionsorder**, välj **Beräkna** för att öppna dialogrutan **Beräkna**.

    ![Dialogrutan Beräkna](./media/subcontract16_estimate-dialog.png)

11. Välj **OK** för att bekräfta beräkningen och återgå till sidan **alla produktionsorder**.

    > [!NOTE]
    > När produktionsorder beräknas genereras inköpsorder S8050 för leverantör US-801.

12. I åtgärdsfönstret, på fliken **tillverkningsorder** väljer du **Strukturlista** för att öppna sidan **Strukturlista** där du kan visa strukturlisterader för tillverkningsordern.

    För serviceartikel S8050 märker du att det finns en hänvisning till inköpsordern som genererades när produktionsordern beräknades.

    ![Produktionsorders strukturrader på sidan Strukturlista](./media/subcontract17_production-order-bom-lines.png)

13. Stäng sidan **Strukturlista** om du vill återgå till sidan **alla produktionsorder**.
14. I åtgärdsfönstret, på fliken **Tidsplan**, välj **Tidsplanera jobb** för att öppna dialogrutan **Finplanering**.
15. Ange följande värden.

    - I fältet **Planeringsriktning**, välj **Framåt från imorgon**.
    - Ange alternativet **begränsad kapacitet** till **Ja**.

    ![Dialogrutan Finplanera](./media/subcontract18_job-scheduling-dialog.png)

16. Välj **OK** för att stänga dialogrutan **finplanering** och återgå till sidan **alla produktionsorder**.
17. I åtgärdsfönstret, på fliken **Tidsplan**, välj **Gantt** för att öppna sidan **Gantt-schema - Resursvy**.

    Gantt-schemat ger en visuell översikt av hur produktionsjobben tidplaneras på resurser. Observera att den externa beläggningsoperationen består av tre jobb: ett processjobb, ett transportjobb och ett kötidjobb.

    ![Gantt-schema i Gantt-schemat - Sida för resursvy](./media/subcontract19_gantt-chart.png)

18. Stäng sidan **Gantt.schema - Resursvy** om du vill återgå till sidan **alla produktionsorder**.
19. I åtgärdsfönstret, på fliken **produktionsorder**, välj **Frisläpp** för att öppna dialogrutan **Frisläpp**.

    ![Dialogrutan Frisläpp](./media/subcontract20_release-dialog.png)

20. Välj **OK** för att stänga dialogrutan **Frisläpp**.
21. Välj **produktionskontroll \> periodiska uppgifter \> frisläpp till lagerställe \> Automatisk frisläppning av strukturliste- och receptrader** för att öppna dialogrutan **Automatisk frisläppning av strukturliste- och receptrader**.

    ![Dialogrutan Automatisk frisläppning av strukturliste- och receptrader](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. Välj **OK** för att köra automatiskt frisläppning av strukturliste- och receptradjobb.

    Det här jobbet frisläpper plockningsarbete av råmaterial till lagret.

23. Välj **produktionskontroll \> produktionsorder \> alla produktionsorder** för att öppna sidan **alla produktionsorder**.
24. Använd fältet för snabbfilter för att välja den tillverkningsorder som du har arbetat med.
25. I åtgärdsfönstret, på fliken **Lagerställe**, välj **Information om arbete** för att öppna sidan **Arbete**.

    Observera att sidan visar två uppsättningar arbete för råmaterialplockning. Första arbetet är för material M8100 och M8101. Dessa material som förbrukas av operation 10. Det andra arbetet är för material M8202 och M8250. Dessa material förbrukas av operation 20, d.v.s. legotillverkningsoperationen.

    ![Två uppsättningar arbete för råmaterialplockning på sidan Arbete.](./media/subcontract22_work-page.png)

26. Starta lagerställeappen för att bearbeta lagerställearbetet för operation 10.

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. Välj **produktionskontroll \> produktionsorder \> alla produktionsorder** för att öppna sidan **alla produktionsorder**.
28. Använd fältet för snabbfilter för att välja den tillverkningsorder som du har arbetat med.
29. I åtgärdsfönstret, på fliken **produktionsorder**, välj **Starta** för att öppna dialogrutan **Starta**.
30. På fliken **Allmänt**, fyll i följande värden:

    - I fältet **Från oper.nr.** välj **10**.
    - I fältet **Till oper.nr.** välj **10**.

    ![Värden som har angetts på fliken Allmänt](./media/subcontract23_start-dialog.png)

31. Välj **OK** för att stänga dialogrutan **Starta** och återgå till sidan **alla produktionsorder**.

    Observera att statusen för produktionsordern nu är **startad**. Materialen för en operation 10 förbrukas av en automatisk bokföring av plocklistejournalen. Tidsförbrukning för operationen 10 redovisas enligt en automatisk bokföring av en flödeskortjournal.

32. Starta lagerställeappen för att bearbeta lagerställearbetet för operation 20.

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. I åtgärdsfönstret, på fliken **produktionsorder**, välj **Starta** för att öppna dialogrutan **Starta**.
34. På fliken **Allmänt**, fyll i följande värden:

    - I fältet **Från oper.nr.** fält, välj **20**.
    - I fältet **Till oper.nr.** fält, välj **20**.
    - I fältet **Kvantitet**, ange **10**.
    - Ange alternativet **Bokför plocklista nu** till **Nej**.

    ![Värden som har angetts på fliken Allmänt](./media/subcontract24_general-tab.png)

35. Välj **OK** för att stänga dialogrutan **Starta** och återgå till sidan **alla produktionsorder**.

    En plocklista har skapats för material som används för beläggningsoperationen och för serviceartikeln. Serviceartikeln motsvarar kostnaden för legotillverkningsoperationen.

36. I åtgärdsfönstret, på fliken **Visa**, välj **Plocklista** för att öppna sidan **Plocklista**.
37. Välj plocklistan som inte har bokförts och markera journalnumret för att visa journalraderna.

    ![Journalrader på sidan Plocklista](./media/subcontract25_picking-list.png)

38. I åtgärdsfönstret, välj **Skriv ut** \> **Rapport över plocklista** för att öppna dialogrutan **Rapport över plocklista**.
39. Ange alternativet **Använd layouten för följesedelsnoteringen** till **Ja**.

    ![Dialogrutan Plocklista - rapport](./media/subcontract26_picking-list-report-dialog.png)

40. Välj **OK** för att generera rapporten **Plocklista**.

    I det här fallet skrivs en leverantörens följesedelsnotering ut för produktionens plocklistejournal. Följesedeln anger det material som levereras till leverantören som ska utföra beläggningsoperationen.

    ![Plocklista - rapport](./media/subcontract27_picking-list-report.png)

41. Stäng rapporten **plocklista** för att återgå till sidan **plocklista**.
42. I åtgärdsfönstret, välj **Bokför** för att öppna dialogrutan **bokför journal**.

    ![Dialogrutan Bokför journal](./media/subcontract28_post-journal-dialog.png)

43. Välj **OK** för att stänga dialogrutan **Bokför journal**.
44. Öppna inköpsordern.

    ![Inköpsordersida](./media/subcontract29_purchase-order-page.png)

45. I åtgärdsfönstret, på fliken **Inköp**, välj **Bekräfta**.
46. Välj **Bokför** för att öppna dialogrutan **Bokför journal**.
47. Välj **OK** för att stänga dialogrutan **Bokför journal** och återgå till sidan **Inköpsorder**.
48. Ändra enhetspriset från **33** till **40**.

    ![Enhetspris ändras på sidan inköpsorder](./media/subcontract30_unit-price.png)

49. Bekräfta inköpsordern igen.
50. Produktinleverans.

    ![Dialogrutan Bokför produktinleverans](./media/subcontract31_posting-product-receipt-dialog.png)

51. Inköpsfaktura.
52. Uppdatera matchningsstatus.

    ![Sidan Leverantörsfaktura](./media/subcontract32_vendor-invoice-page.png)

53. Rapportera som färdig.

    ![Dialogrutan Rapportera som färdigt](./media/subcontract33_report-as-finished-dialog.png)

54. Slut.

    ![Dialogrutan Slut](./media/subcontract34_end-dialog.png)

55. Kostnadsjämförelse.

    ![Kostnadsjämförelsediagram](./media/subcontract35_cost-comparison-charts.png)

Inställning saknas i data.
