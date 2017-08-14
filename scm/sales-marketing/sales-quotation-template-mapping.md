---
title: "Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera huvuden och rader i försäljningsofferter från Microsoft Dynamics 365 for Sales till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
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
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 172a3da1b6d90a25ea9ebd14265e70e4a6f9bd70
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a>Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration). 

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera huvuden och rader i försäljningsofferter från Microsoft Dynamics 365 for Sales (Sales) till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations). 

## <a name="template-and-tasks"></a>Mall och uppgifter

Följande mallar och underliggande uppgifter används för att synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations:

- **Mallens namn:** försäljningsofferter (Sales till Fin and Ops)
- **Namn på aktiviteter i projektet:**

    - QuoteHeader
    - QuoteLine

Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsofferter kan uppstå:

- Produkter
- Konton (om de används)
- Kontakter (om de används)

## <a name="entity-set"></a>Ange entiteten

| Försäljning        | CDS           | Finance and Operations    |
|--------------|---------------|---------------------------|
| Citat       | Offert     | Försäljningsoffertrubriker   |
| QuoteDetails | QuotationLine | Försäljningsoffertrader för CDS |

## <a name="entity-flow"></a>Flöde för entitet

Försäljningsofferter skapas i Sales och synkroniseras till Finance and Operations.

Försäljningsofferter från Sales synkroniseras endast om följande villkor är uppfyllda:

- Alla produkter på försäljningsoffertraderna hanteras externt.
- Försäljningsofferten är aktiv eller aktiverad.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

Fältet **Har endast externt hanterade produkter** har lagts till offertentiteten för att konstant spåra om försäljningsofferten helt består av externt underhållna produkter. Om en försäljningsoffert endast har externt underhållna produkter, underhålls produkter i Finance and Operations. Detta beteende hjälper till att garantera att du inte försöker synkronisera försäljningsoffertraderna med produkter som är okända för Finance and Operations.

Alla produkter och rader på offerten uppdateras med informationen **Har endast externt hanterade produkter** från offerthuvudet. Den här informationen finns i fältet **Offerten har endast externt hanterade produkter** på offertradentiteten.

Fälten **rabatt**, **tillägg**, och **moms** styrs av en komplex inställning i Finance and Operations. Den här inställningen stöder inte integreringsmappning. I den aktuella designen hanteras fälten **pris**, **rabatt**, **tillägg**, och **moms** av Finance and Operations.

I Sales gör lösningen följande fält skrivskyddade, eftersom värdena inte ska synkroniseras till Finance and Operations:

- **Skrivskyddade fält på försäljningsoffertens huvud:** rabatt % rabatt, Fraktbelopp
- **Skrivskyddade fält på försäljningsoffertraderna:** moms

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

- Innan du synkroniserar försäljningsofferter, går du i Sales tilll **Inställningar** &gt; **Administration** &gt; **Systeminställningar** &gt; **Försäljning** och kontrollerar att fältet **rabattberäkningsmetod** är inställt på **Per enhet**. Den här inställningen hjälper till att garantera att radartikelrabatt från Sales motsvarar inställningen i Finance and Operations. I annat fall kommer inte rabatten att vara korrekt i Finance and Operations, eftersom Finance and Operations läser rabatten som en rabatt per enhet även om den vore en rabatt per rad i Sales.
- I Finance and Operations, gå till **kundreskontra** &gt; **inställningar** &gt; **kundreskontraparametrar**. På fliken **nummerserie** markerar du nummerserien för försäljningsofferter och klickar sedan på **Visa detaljer**. Sedan under **allmänna inställningar**, anger du fältet **manuell** till **Ja**.
- I Finance and Operations, gå till **kundreskontra** &gt; **inställningar** &gt; **kundreskontraparametrar**. Klicka sedan på fliken **försändelser** och ange fältet **Leveransdatumkontroll** till **ingen**. Den här inställningen förhindrar synkroniseringsfel för försäljningsofferter.

### <a name="quoteheader"></a>QuoteHeader

- Fältet **begärt leveransdatum** krävs i Finance and Operations och men synkroniseringen misslyckas om fältet lämnas tomt. För att undvika det här problemet om fältet är tomt kan ett standarddatum hämtas från **källa &gt; CDS**. Datumet ska uppdateras till ett önskat värde. För närvarande kan du inte ange ett värde som **idag** för att representera dagens datum. Du måste ange ett specifikt datum. Standardvärdemallen för **begärt leveransdatum** är **1/1/2020**.
- Fältet **adress landskod** krävs i Finance and Operations. Du kan ange ett standardvärde som ska användas om fältet lämnas tomt i Sales om du vill förhindra synkroniseringsfel. Standardvärdet är också användbart eftersom du inte behöver ange ett värde i fältet **land** för lokala adresser. Det finns inget standardmallvärde för **DeliveryAddressCountryRegionISOCode**.
- Uppdatera mappning för **CDS-organisations-ID** i **källa &gt; CDD** så att den matchar **CDS-organisation** i organisationsentiteten:

    - Standardvärdet för mallen **Organization_OrganizationId** är **ORG001**.
    - Standardvärdet för mallen **Account_Organization_OrganizationId** är **ORG001**.
    - Standardvärdet för mallen **InvoiceAccount_OrganizationId** är **ORG001**.

### <a name="quoteline"></a>QuoteLine

- Uppdatera mappning för **CDS-organisations-ID** i **källa &gt; CDD** så att den matchar **CDS-organisation** i organisationsentiteten:

    - Standardvärdet för mallen **Organization_OrganizationId** är **ORG001**.
    - Standardvärdet för mallen **Product_Organization_Organization_OrganizationId** är **ORG001**.
    - Standardvärdet för mallen **Quotation_Organization_Organization_OrganizationId** är **ORG001**.

- Fältet **begärt leveransdatum** krävs i Finance and Operations och men synkroniseringen misslyckas om fältet lämnas tomt. För att undvika det här problemet om fältet är tomt kan ett standarddatum hämtas från **källa &gt; CDS**. Datumet ska uppdateras till ett önskat värde. För närvarande kan du inte ange ett värde som **idag** för att representera dagens datum. Du måste ange ett specifikt datum. Standardvärdemallen för **begärt leveransdatum** är **1/1/2020**.
- Du kan lägga till följande mappningar från **CDS &gt; Destination** för att garantera att offertraderna importeras till Finance and Operation om det inte finns någon standardinformation från varken kunden eller produkten:

    - **SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations. Det finns inget standrdmallvärde för **SiteId**.
    - **WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Finance and Operations. Det finns inget standrdmallvärde för **WarehouseId**.

- Kontrollera att nödvändig värdemappningen för den säljande enheten (UOM) i  Finance and Operations finns i mappningen **CDS &gt; Destination** för **Quantity_UOM** till **SALESUNITSYMBOL**.

## <a name="template-mapping-in-data-integrator"></a>Mallmappning i dataintegratör

> [!NOTE]
> - Fälten **rabatt**, **tillägg**, och **moms** styrs av en komplex inställning i Finance and Operations. Den här inställningen stöder inte integreringsmappning. I den aktuella designen hanteras fälten **pris**, **rabatt**, **tillägg**, och **moms** av Finance and Operations.
> - Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.

I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.

### <a name="quoteheader"></a>QuoteHeader

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a>QuoteLine

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mallmappning i dataintegratör](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Relaterade ämnen

[Synkronisera produkter från Finance and Operations till produkter i Sales](products-template-mapping.md)

[Synkronisera konton från Sales till kunder i Finance and Operations](accounts-template-mapping.md)

[Synkronisera kontakter från Sales till kontakter i Finance and Operations](contacts-template-mapping.md)



