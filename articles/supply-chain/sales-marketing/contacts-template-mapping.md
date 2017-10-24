---
title: "Synkronisera kontakter från Sales till kontakter i Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera kontakt (kontakter) och kontakt (kunder) från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 41e27776b94df059ada13efb9a3dbf6a29d67f36
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Synkronisera kontakter från Sales till kontakter i Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](/common-data-service/entity-reference/dynamics-365-integration). 

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera kontakt (kontakter) och kontakt (kunder) från Microsoft Dynamics 365 for Sales (Sales) till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).

## <a name="templates-and-tasks"></a>Mallar och uppgifter

Följande mallar och underliggande uppgifter används för att synkronisera kontakt (kontakter) i Sales och kontakt (kunder) i Finance and Operations:

- **Namn på mallar:**

    - Kontakter (Sales till Fin and Ops)
    - Kontakter till kund (Sales till Fin and Ops)

- **Namn på aktiviteter i projektet:**

    - Kontakter
    - ContactToCustomer

Följande synkroniseringsuppgift krävs före kontaktsynkronisering: konton (Sales till Fin and Ops)

## <a name="entity-sets"></a>Entitetsuppsättningar

| Försäljning    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Kontakter | Kontakt | CDS-kontakter           |
| Kontakter | Konto | Kunder V2           |

## <a name="entity-flow"></a>Flöde för entitet

Kontakter hanteras i Sales och synkroniseras till Common Data Service (CDS) och Finance and Operations.

En kontakt i Sales kan bli en kontakt i CDS och Finance and Operations. Alternativt kan den bli ett konto i CDS och en kund i Finance and Operations. Du tar reda på om en kontakt ska öppnas i försäljning för synkronisering av CDS och Finance and Operations (till exempel kontakter i Sales &gt; kontakter i CDS &gt; kontakter i Finance and Operations), systemet tittar på följande egenskaper på en kontakt i Sales:

- **Synkronisera till konto i CDS och kundinformation i Finance and Operations:** kontakter där **är aktiv kund** anges till **Ja**
- **Synkronisera kontakt i CDS och kontaktinformation i Finance and Operations:** kontakter där **är aktiv kund** anges till **nr** och **företag** (överordnat konto/kontakt) leder till ett konto (inte en kontakt)

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales 

Ett nytt fält för **är aktiv kund** har lagts till kontakten. Det här fältet används för att urskilja kontakter vars försäljningsaktivitet och kontakter som inte har en försäljningsaktivitet. **Är aktiv kund** anges till **Ja** endast för kontakter som har relaterade offerter, order eller fakturor. Endast dessa kontakter synkroniseras till Finance and Operations som kunder.

Ett nytt fält för **IsCompanyAnAccount** har lagts till kontakten. Det här fältet används för att ange om en kontakt är kopplad till ett företag (överordnat konto eller kontakt) av typen **konto**. Denna information används för att identifiera kontakter som ska synkroniseras mot Finance and Operations som kontakter.

Ett nytt fält för **kontaktnummer** har lagts till kontakten för att garantera en naturlig och unik nyckel för integration. När en ny kontakt skapas kommer **kontaktnummer**-värde genereras automatiskt med hjälp av en nummerserie. Värdet består av **CON** följt av en ökande nummerserie och sedan ett suffix på sex tecken. Här är ett exempel: **CON-01000-BVRCPS**

När integrationslösningen för Sales läggs till i Sales, anger ett uppgraderingsskript fältet **kontaktnummer** för befintliga kontakter med nummerserien som beskrevs tidigare. Uppgraderingsskriptet anger också fältet **är aktiv kund** till **Ja** för alla kontakter som har försäljningsaktivitet.

## <a name="in-finance-and-operations"></a>I Finance and Operations 

Kontakter är märkta med egenskapen **IsContactPersonExternallyMaintained**. Den här egenskapen anger att en kontakt hanteras externt. I det här fallet underhålls externt underhållna kontakter i Sales.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

### <a name="contact-to-contact"></a>Kontakt till kontakt

- Uppdatera **CDS organisations-ID** i **källa -&gt; CDS**-mappning.

    - Standardvärdet för mallen **Organization_OrganizationId [Organization ID]** är **ORG001**.
    - Standardvärdet för mallen **PrimaryAccount_Organization_OrganizationId [Organization ID]** är **ORG001**.

- Fältet **adress landskod** krävs i Finance and Operations. För att undvika problem med synkronisering kan du ange ett standardvärde i **CDS &gt;Operations**-mappning. Detta standardvärde används sedan om fältet lämnas tomt i Sales. Standardvärdet för mallen **PrimaryAddressCountryRegionISOCode** är **USA**.
- Kontrollera att det finns ett värde för följande fält i Finance and Operations. Om informationen inte krävs i Finance and Operations kan du ta bort mappningen från **CDS &gt;Destination**-mappning.

    - **Fältnamn i Finance and Operations:** beslut
    - **Mappning:** PrimaryAccountRole = DecisionMakingRole

### <a name="contact-to-customer"></a>Kontakt till kund

- Uppdatera **CDS organisations-ID** i **källa -&gt; CDS**-mappning. Standardvärdet för mallen **Organization_OrganizationId [Organization ID]** är **ORG001**.
- Fältet **adress landskod** krävs i Finance and Operations. För att undvika problem med synkronisering kan du ange ett standardvärde i **CDS &gt;Destination**-mappning. Detta standardvärde används sedan om fältet lämnas tomt i Sales. Standardvärdet för mallen **PrimaryAddressCountryRegionISOCode** är **USA**.
- **Kundgrupp** krävs i Finance and Operations. För att undvika problem med synkronisering kan du ange ett standardvärde i **CDS &gt;Destination**-mappning. Detta standardvärde används sedan om fältet lämnas tomt i Sales. Standardmallvärdet för **CustomerGroupId** är **10**.
- Genom att lägga till följande mappningar från **CDS &gt; Destination**, kan du minska antalet manuella uppdateringar som krävs för Finance and Operations. Du kan använda ett standardvärde eller värdekarta från, till exempel **Land/Region** eller **ort**.

    - **SiteId** - en standardplats kan också definieras på produkter i Finance and Operations. En plats måste anges för att skapa offerter och försäljningsorder i Finance and Operations. Ett mallvärde för **SiteId** är inte definierad.
    - **WarehouseId** - ett standardlagerställe kan också definieras på produkter i Finance and Operations. Ett lagerställe måste anges för att skapa offerter och försäljningsorder i Finance and Operations. Ett mallvärde för **WarehouseId** är inte definierad.
    - **LanguageId** – ett språk måste anges för att skapa offerter och försäljningsorder i Finance and Operations. Standardvärdet för mallen **LanguageId** är **en-us**.

## <a name="template-mapping-in-data-integrator"></a>Mallmappning i dataintegratör

I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.

### <a name="contact-to-contact"></a>Kontakt till kontakt

![Mallmappning i dataintegratör](./media/contacts-template-mapping-data-integrator-1.png)

![Mallmappning för kontakter i dataintegratör](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a>Kontakt till kund

![Mallmappning i dataintegratör](./media/contacts-template-mapping-data-integrator-3.png)

![Mallmappning för kontakter i dataintegratör](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Relaterade ämnen

[Synkronisera produkter från Finance and Operations till produkter i Sales](products-template-mapping.md)

[Synkronisera konton från Sales till kunder i Finance and Operations](accounts-template-mapping.md)

[Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations](sales-quotation-template-mapping.md)

[Synkronisera huvuden och rader i försäljningsorder från Finance and Operations till Sales](sales-order-template-mapping.md)

[Synkronisera huvuden och rader i försäljningsfakturor från Finance and Operations till Sales](sales-invoice-template-mapping.md)

