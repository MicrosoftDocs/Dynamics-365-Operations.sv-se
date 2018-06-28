---
title: "Synkronisera arbetsorder i Field Service till försäljningsorder i Finance and Operations"
description: "Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder i Field Service till försäljningsorder i Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 8914723f6ef436bfc9e3a98cc82d5486042b0761
ms.openlocfilehash: 250b7caa1e1495140d0d4f688ecae4acb8814467
ms.contentlocale: sv-se
ms.lasthandoff: 06/07/2018

---

# <a name="synchronize-work-orders-in-field-service-to-sales-orders-in-finance-and-operations"></a>Synkronisera arbetsorder i Field Service till försäljningsorder i Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vilka mallar och underliggande uppgift som används för att synkronisera arbetsorder i Microsoft Dynamics 365 for Field Service till försäljningsorder i Microsoft Dynamics 365 for Finance and Operations.

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera arbetsorder i Field Service till försäljningsorder i Finance and Operations.

## <a name="templates-and-tasks"></a>Mallar och uppgifter

Följande mallar och underliggande uppgifter används för att köra synkronisering av arbetsorder i Field Service till försäljningsorder i Finance and Operations.

### <a name="names-of-the-templates-in-data-integration"></a>Namn på mallar i dataintegrering

Mallen **Arbetsorder till försäljningsorder (Field Service till Fin and Ops)** används för att köra synkroniseringen.

### <a name="names-of-the-tasks-in-the-data-integration-project"></a>Namnen på uppgifterna i dataintegreringsprojektet

- WorkOrderHeader
- WorkOrderServiceLineEstimate
- WorkOrderServiceLineUsed
- WorkOrderProductLineEstimate
- WorkOrderProductLineUsed

Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsorder kan uppstå:

- Fältserviceprodukter (Fin and Ops till Field Service)
- Konton (Sales till Fin and Ops) - Direkt

## <a name="entity-set"></a>Ange entiteten

| **Field Service** | **Finance and Operations** |
|-------------------------|-------------------------|
| msdyn_workorders        | CDS-försäljningsorderrubrik |
| msdyn_workorderservices | CDS-försäljningsorderrader   |
| msdyn_workorderproducts | CDS-försäljningsorderrader   |

## <a name="entity-flow"></a>Flöde för entitet

Arbetsorder skapas i Field Service. Om arbetsorder endast innehåller externt underhållna produkter och om värdet för **Arbetsorderstatus** skiljer sig från **Öppen - Ej schemalagd** och **Stängda – Annullerade** kan arbetsordern synkroniseras till Finance and Operations via ett CDS-dataintegreringsprojekt. Uppdateringar i arbetsordern synkroniseras som försäljningsorder i Finance and Operations. Dessa uppdateringar omfattar information om ursprungstyp och status.

## <a name="estimated-versus-used"></a>Uppskattad jämfört med Använd

I Field Service har produkter och tjänster för arbetsorder både värden **uppskattad** och **använd** för kvantiteter och belopp. I Finance and Operations har emellertid försäljningsorder inte samma begrepp av värdena **uppskattad** och **använd**. För att stödja produktallokering som använder den förväntade kvantiteten på försäljningsordern i Finance and Operations, men att behålla den använda kvantiteten som ska förbrukas och faktureras synkroniserar två uppsättningar uppgifter de produkter och tjänster som finns i arbetsordern. En uppsättning uppgifter avser värdet **uppskattad** och en annan uppsättning uppgifter avser värdet **använd**.

Detta beteende tillåter scenarier där uppskattade värden används för allokering eller reservation i Finance and Operations medan använda värden används för förbrukning och fakturering.

### <a name="estimated"></a>Uppskattat

För synkronisering av produktrader används värdet **uppskattad** när värdet **radstatus** är **uppskattad**, alternativet **tilldelad** anges till **Ja** och värdet **Systemstatus** inte är **Stängd - Bokförd**.

För synkronisering av tjänstrader används värdet **uppskattad** när värdet **radstatus** är **uppskattad** och värdet **systemstatus** inte är **Stängd - Bokförd**.

### <a name="used"></a>Används

Värdet **använd** används för förbrukning och fakturering. I dessa fall synkroniseras **använd**.

Följande tabell ger en översikt över de olika kombinationerna för produktrader.

| Systemstatus <br>(Field Service) | Radstatus <br>(Field Service) | Fördelat <br>(Field Service) |Synkroniserat värde <br>(Finance and Operations) |
|--------------------|-------------|-----------|---------------------------------|
| Öppen - Schemalagd   | Uppskattat   | Ja       | Uppskattat                       |
| Öppen - Schemalagd   | Uppskattat   | Nr        | Används                            |
| Öppen - Schemalagd   | Används        | Ja       | Används                            |
| Öppen - Schemalagd   | Används        | Nr        | Används                            |
| Öppen - Pågår | Uppskattat   | Ja       | Uppskattat                       |
| Öppen - Pågår | Uppskattat   | Nr        | Används                            |
| Öppen - Pågår | Används        | Ja       | Används                            |
| Öppen - Pågår | Används        | Nr        | Används                            |
| Öppen - Slutförd   | Uppskattat   | Ja       | Uppskattat                       |
| Öppen - Slutförd   | Uppskattat   | Nr        | Används                            |
| Öppen - Slutförd   | Används        | Ja       | Används                            |
| Öppen - Slutförd   | Används        | Nr        | Används                            |
| Stängd - Bokförd    | Uppskattat   | Ja       | Används                            |
| Stängd - Bokförd    | Uppskattat   | Nr        | Används                            |
| Stängd - Bokförd    | Används        | Ja       | Används                            |
| Stängd - Bokförd    | Används        | Nr        | Används                            |

Följande tabell ger en översikt över de olika kombinationerna för tjänstrader.

| Systemstatus <br>(Field Service) | Radstatus <br>(Field Service) | Synkroniserat värde <br>(Finance and Operations) |
|--------------------|-------------|-----------|
| Öppen - Schemalagd   | Uppskattat   | Uppskattat |
| Öppen - Schemalagd   | Används        | Används      |
| Öppen - Pågår | Uppskattat   | Uppskattat |
| Öppen - Pågår | Används        | Används      |
| Öppen - Slutförd   | Uppskattat   | Uppskattat |
| Öppen - Slutförd   | Används        | Används      |
| Stängd - Bokförd    | Uppskattat   | Används      |
| Stängd - Bokförd    | Används        | Används      |

Synkronisering av värdet **uppskattad** jämfört med värdet **använd** hanteras via två uppsättningar med uppgifter för produktrader och tjänstrader. Fördefinierade filter utlöser korrekt uppgift och den underliggande mappningen kan garantera att de korrekta värdena för **förväntad** jämfört med **använd** synkroniseras.

### <a name="example"></a>Exempel

1. En arbetsorder skapat och schemaläggs i Field Service.

    Värdet **systemstatus** är **öppen – schemalagd**.

    - **Produktrad:** uppskattad kvantitet = 5ea, använd kvantitet = 0ea, radstatus = uppskattad, tilldelad = Nej
    - **Servicerad:** uppskattad kvantitet = 2 tim, använd kvantitet = 0 tim, radstatus = uppskattad

    I detta exempel synkroniseras produktens värde för**Använd kvantitet** **0** (noll) och tjänstens värde för **Uppskattad kvantitet** är **2 tim** till Finance and Operations.

2. Produkter fördelas i Field Service.

    Värdet **systemstatus** är **öppen – schemalagd**.

    - **Produktrad:** uppskattad kvantitet = 5ea, använd kvantitet = 0ea, radstatus = uppskattad, tilldelad = Ja
    - **Servicerad:** uppskattad kvantitet = 2 tim, använd kvantitet = 0 tim, radstatus = uppskattad

    I detta exempel synkroniseras produktens värde för**Uppskattad kvantitet** **5ea** och tjänstens värde för **Uppskattad kvantitet** är **2 tim** till Finance and Operations.

3. Serviceteknikern börjar arbeta på arbetsorder och registrerar materialanvändningen 6.

    Värdet **systemstatus** är **Öppen – Pågår**.

    - **Produktrad:** uppskattad kvantitet = 5ea, använd kvantitet = 6ea, radstatus = använd, tilldelad = Ja
    - **Servicerad:** uppskattad kvantitet = 2 tim, använd kvantitet = 0 tim, radstatus = uppskattad

    I detta exempel synkroniseras produktens värde för**Använd kvantitet** **6** och tjänstens värde för **Uppskattad kvantitet** är **2 tim** till Finance and Operations.

4. Serviceteknikern slutför arbetsordern och registerar använd tid till 1,5 timmar.

    Värdet **systemstatus** är **öppen – Slutförd**.

    - **Produktrad:** uppskattad kvantitet = 5ea, använd kvantitet = 6ea, radstatus = använd, tilldelad = Ja
    - **Servicerad:** uppskattad kvantitet = 2 tim, använd kvantitet = 1,5 tim, radstatus = använd

    I detta exempel synkroniseras produktens värde för**Använd kvantitet** **6** och tjänstens värde för **Använd kvantitet** är **1,5 tim** till Finance and Operations.

## <a name="sales-order-origin-and-status"></a>Försäljningorderns ursprung och status

### <a name="sales-origin"></a>Försäljningsursprung

Om du vill hålla reda på försäljningsorder i Finance and Operations som kommer från arbetsorder kan du skapa försäljningsursprung där alternativet **Tilldelning av ursprungstyp** är inställd på **Ja** och **Typ av försäljningsursprung** är inställd på **Integrering av arbetsorder**.

Som standard väljer mappningen försäljningsursprung för försäljningsursprungstypen **Integrering av arbetsorder** för alla försäljningsorder som skapas från arbetsorder. Detta kan vara användbart när du arbetar med försäljningsorder i Finance and Operations. Du måste se till att försäljningsorder kommer från arbetsorder inte synkroniseras tillbaka till Field Service som arbetsorder.

Mer information om hur du skapar korrekt inställning av försäljningsursprung i Finance and Operations finns i avsnittet ”Ställa in mappning och förutsättningar” i det här avsnittet.

### <a name="status"></a>Status

När försäljningsordern har sitt ursprung i en arbetsorder, visas fältet **Status för extern arbetsorder** på flikar **Inställningar** på försäljningsorderns rubrik. Detta fält visar systemstatus från arbetsorder i Field Service för att spåra synkroniserade arbetsorderstatus för försäljningsorder i Finance and Operations. Fältet kan också hjälpa användare av Finance and Operations att avgöra när försäljningsordern ska levereras eller faktureras.

Fältet **extern arbetsorderstatus** kan ha följande värden:

- Öppen - Schemalagd
- Öppen - Pågår
- Öppen - Slutförd
- Stängd - Bokförd

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service

För att stödja integrationen mellan Field Service och Finance and Operations krävs ytterligare funktioner från Field Service CRM-lösning. Lösningen omfattar följande ändringar.

### <a name="work-order-entity"></a>Arbetsorderentitet

Fältet **har endast externt hanterade produkter** har lagts till i entiteten **arbetsorder** och visas på sidan. Den används för att spåra om en arbetsorder enbart består av produkter som hanteras externt. En arbetsorder helt består av externt underhållna produkter när alla relaterade produkter underhålls i Finance and Operations. Detta fält hjälper till att garantera att användare inte synkroniserar arbetsorder som har produkter som är okända för Finance and Operations.

### <a name="work-order-product-entity"></a>Produktentitet för arbetsorder

- Fältet **Order har endast externt hanterade produkter** har lagts till i entiteten **arbetsorderprodukt** och visas på sidan. Den används för att spåra om arbetsorderprodukt underhålls i Finance and Operations. Detta fält hjälper till att garantera att användare inte synkroniserar arbetsorderprodukter som är okända för Finance and Operations.
- Fältet **Systemststus rubrik** har lagts till i entiteten **arbetsorderprodukt** och visas på sidan. Används för att spåra systemstatus för arbetsordern och hjälper till att säkerställa korrekt filtrering om när arbetsorderprodukter synkroniseras till Finance and Operations. När filter ställs in på integrationsuppgifter, används också **systemstatusrubrikens** information för att bestämma om uppskattad eller använda värden ska synkroniseras.
- Fältet **fakturerat enhetsbelopp** visar det belopp som ska faktureras per faktisk enhet som används. Värdet beräknas som värdet **totalbelopp** delat med värdet **faktiska antalet**. Fältet används för integrering med system som inte stöder olika värden för den använda kvantiteten och den fakturerade kvantiteten. Det här fältet visas inte i användargränssnittet (UI). 
- Fältet **fakturerat rabattbelopp** beräknas som värdet **rabattbelopp** plus avrundning från beräkningen av värdet **fakturerat enhetsbelopp**. Det här fältet används för integrering och visas inte i användargränssnittet.
- Fältet **antal decimaler** innehåller värdet från fältet **kvantitet** som ett decimaltal. Det här fältet används för integrering och visas inte i användargränssnittet. 
- Värdet i fältet **använd** återställs till **0** (noll) om värdet **radstatus** för arbetsorderprodukt ändras från **används** till **uppskattad**. Den här ändringen hjälper till att undvika situationer där kvantiteten av misstag används för synkronisering när värdet **radstatus** är **uppskattad** och **fördelat** är inställt på **nej**.

### <a name="work-order-service-entity"></a>Tjänstentitet för arbetsorder

- Fältet **Order har endast externt hanterade produkter** har lagts till i entiteten **arbetsordertjänst** och visas på sidan. Den används för att spåra om arbetsordertjänst underhålls i Finance and Operations. Detta fält hjälper till att garantera att användare inte synkroniserar arbetsordertjänster som är okända för Finance and Operations.
- Fältet **Systemststus rubrik** har lagts till i entiteten **arbetsordertjänst** och visas på sidan. Används för att spåra systemstatus för arbetsordern och hjälper till att säkerställa korrekt filtrering om när arbetsordertjänster synkroniseras till Finance and Operations. När filter ställs in på integrationsuppgifter, används också **systemstatusrubrikens** information för att bestämma om uppskattad eller använda värden ska synkroniseras.
- Fältet **varaktighet i timmar** innehåller värdet från fältet **varaktighet** när värdet konverteras från minuter till timmar. Det här fältet används för integrering och visas inte i användargränssnittet.
- Fältet **Uppskattad varaktighet i timmar** innehåller värdet från fältet **Uppskattad varaktighet** när värdet konverteras från minuter till timmar. Det här fältet används för integrering och visas inte i användargränssnittet.
- Fältet **fakturerat enhetsbelopp** lagrar det belopp som ska faktureras per faktisk enhet som används. Värdet beräknas som värdet **totalbelopp** delat med värdet **faktiska antalet**. Fältet används för integrering med system som inte stöder olika värden för den använda kvantiteten och den fakturerade kvantiteten. Det här fältet visas inte i användargränssnittet (UI).
- Fältet **fakturerat rabattbelopp** beräknas som värdet **rabattbelopp** plus avrundning från beräkningen av värdet **fakturerat enhetsbelopp**. Det här fältet används för integrering och visas inte i användargränssnittet.
- Fältet **Extern radorder** är ett beräknat negativt radordernummer som kan användas i externa system där arbetsorderprodukt och tjänstrader kombineras. Detta fältet låter arbetsorderprodukter infogas för att ha positiva radnummer och arbetsordertjänster med negativt radnummer. Värdet i det här fältet beräknas som värdet **Radorder** multiplicerat med -1. Det här fältet visas inte i användargränssnittet (UI).
- Värdet i fältet **använd** återställs till **0** (noll) om värdet **radstatus** för arbetsordertjänst ändras från **används** till **uppskattad** av någon anledning. Den här ändringen hjälper till att undvika situationer där kvantiteten av misstag används för synkronisering när värdet **radstatus** är **uppskattad** och värdet **systemstatus rubrik** är **Stängd - Bokförd**.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

Innan du synkroniserar arbetsorder är det viktigt att du uppdaterar följande inställningar i systemen.

### <a name="setup-in-field-service"></a>Inställning i Field Service

- Kontrollera att den nummerserie som används för arbetsorder i Field Service inte överlappar den nummerserie som ska användas för försäljningsorder i Finance and Operations. I annat fall kan befintliga försäljningsorder uppdateras felaktigt i Field Service eller Finance and Operations.
- Fältet **Skapa arbetsorderfaktura** måste ställas in på **aldrig**, eftersom faktureringen görs från Finance and Operations. Gå till **Field Service**\>**inställningar**\>**Administration**\>**Field Service-inställningar**, och kontrollera att fältet **Skapa arbetsorderfaktura** anges till **aldrig**.

### <a name="setup-in-finance-and-operations"></a>Inställningar i Finance and Operations

Integrationen av arbetsorder kräver att du ställer in försäljningsursprunget. Försäljningsursprunget används för att särskilja försäljningsorder i Finance and Operations som skapats från arbetsorder i Field Service. När försäljningsordern har sitt försäljningsursprung av typen **Integrering av arbetsorder** visas fältet **Extern arbetsorderstatus** på försäljningsorderns rubrik. Dessutom hjälper försäljningsursprunget till att garantera att försäljningsorder som har skapats från arbetsorder i Field Service filtreras bort under synkroniseringen från Finance and Operations till Field Service.

1. Gå till **Försäljning och marknadsföring** \> **Inställningar** \> **Försäljningsorder** \> **Alla försäljningsorder**.
2. Välj **Ny** för att skapa ett nytt försäljningsursprung.
3. I fältet **Försäljningsursprung** anger du ett namn för försäljningsursprung som t.ex. **Arbetsorder**.
4. I fältet **Beskrivning** anger du en beskrivning såsom **Arbetsorder för Field Service**.
5. Markera kryssrutan **Tilldelning av ursprungstyp**.
6. Ange fältet **Typ av försäljningsursprung** till **Integration av arbetsorder**.
7. Välj **Spara**.


### <a name="setup-in-data-integration"></a>Konfigurera i dataintegration

Kontrollera att **integreringsnyckel** finns i **msdyn_workorders**
1. Gå till dataintegration
2. Välj fliken **Anslutningsinställning**
3. Välj anslutningsinställning som används för arbetsordersynkronisering
4. Välj fliken **Integreringsnyckel**
5. Söka efter msdyn_workorders och kontrollera att nyckeln **msdyn_name (ordernummer arbete)** läggs till. Om den inte visas lägger du till den genom att klicka på **Lägg till nyckel** och på **spara** längst upp på sidan

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderheader"></a>Arbetsorder till försäljningsorder (Field Service till Fin and Ops): WorkOrderHeader

Filter: (msdyn_systemstatus ne 690970005) och (msdyn_systemstatus ne 690970000) och (msdynce_hasexternallymaintainedproductsonly eq true)

[![Mallmappning i dataintegrering](./media/FSWorkOrder1.png )](./media/FSWorkOrder1.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderservicelineestimate"></a>Arbetsorder till försäljningsorder (Field Service till Fin and Ops): WorkOrderServiceLineEstimate

Filter: (msdynce_headersystemstatus ne 690970005) och (msdynce_headersystemstatus ne 690970000) och (msdynce_orderhasexternalmaintainedproductsonly eq true) och (msdyn_linestatus eq 690970000) och (msdynce_headersystemstatus ne 690970004)

[![Mallmappning i dataintegrering](./media/FSWorkOrder2.png )](./media/FSWorkOrder2.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderservicelineused"></a>Arbetsorder till försäljningsorder (Field Service till Fin and Ops): WorkOrderServiceLineUsed

Filter: (msdynce_headersystemstatus ne 690970005) och (msdynce_headersystemstatus ne 690970000) och (msdynce_orderhasexternalmaintainedproductsonly eq true) och ((msdyn_linestatus eq 690970001) eller (msdynce_headersystemstatus eq 690970004))

[![Mallmappning i dataintegrering](./media/FSWorkOrder3.png )](./media/FSWorkOrder3.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderproductlineestimate"></a>Arbetsorder till försäljningsorder (Field Service till Fin and Ops): WorkOrderProductLineEstimate

Filter: (msdynce_headersystemstatus ne 690970005) och (msdynce_headersystemstatus ne 690970000) och (msdynce_orderhasexternalmaintainedproductsonly eq true) och (msdyn_linestatus eq 690970000) och (msdynce_headersystemstatus ne 690970004) och (msdyn_allocated eq true)

[![Mallmappning i dataintegrering](./media/FSWorkOrder4.png )](./media/FSWorkOrder4.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderproductlineused"></a>Arbetsorder till försäljningsorder (Field Service till Fin and Ops): WorkOrderProductLineUsed

Filter: (msdynce_headersystemstatus ne 690970005) och (msdynce_headersystemstatus ne 690970000) och (msdynce_orderhasexternalmaintainedproductsonly eq true) och ((msdyn_linestatus eq 690970001) eller (msdynce_headersystemstatus eq 690970004) eller (msdyn_allocated ne true))

[![Mallmappning i dataintegrering](./media/FSWorkOrder5.png )](./media/FSWorkOrder5.png)

