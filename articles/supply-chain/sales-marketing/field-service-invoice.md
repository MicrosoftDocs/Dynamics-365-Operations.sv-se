---
title: Synkronisera avtalsfakturor i Field Service till fristextfakturor i Finance and Operations
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgift som används för att synkronisera avtalsfakturor i Microsoft Dynamics 365 for Field Service till fritextfakturor i Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: ace66c037953f4b1b2e8b93a315faefdb090b1eb
ms.openlocfilehash: 6672e283a5e56b068e3494d53a0fd6dd08253ba9
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-finance-and-operations"></a>Synkronisera avtalsfakturor i Field Service till fristextfakturor i Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vilka mallar och underliggande uppgift som används för att synkronisera avtalsfakturor i Microsoft Dynamics 365 for Field Service till fritextfakturor i Microsoft Dynamics 365 for Finance and Operations.

## <a name="templates-and-tasks"></a>Mallar och uppgifter

Följande mall och underliggande uppgifter används för att köra synkronisering av avtalsfakturor från Field Service till fritextfakturor i Finance and Operations.

**Namnet på mallen i dataintegreringen**

- Avtalsfakturor (Field Service till Fin and Ops)

**Namnen på uppgifterna i dataintegreringsprojektet:**

- Fakturarubriker
- Fakturarader

Följande synkroniseringsuppgifter krävs före synkronisering av avtalsfakturor kan uppstå:

- Konton (Sales till Fin and Ops) - Direkt

## <a name="entity-set"></a>Ange entiteten

| Field Service  | Finance and Operations                 |
|----------------|----------------------------------------|
| fakturor       | Fakturahuvuden i fritext för CDS-kund |
| fakturainformation | Fakturarader i fritext för CDS-kund   |

## <a name="entity-flow"></a>Flöde för entitet

Fakturor som har skapats från ett avtal i Field Service kan synkroniseras till Finance and Operations via ett Common Data Service (CDS) dataintegreringsprojekt. Uppdateringar till dessa fakturor synkroniseras till fritextfakturor i Finance and Operations om redovisningsstatus för fritextfakturor är **pågående**. Efter fritextfakturorna bokförs i Finance and Operations och redovisningsstatus uppdateras till **slutförd**, kan du inte längre synkronisera uppdateringar från Field Service.

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service

Fältet **Har rader med avtalsursprung** har lagts till i entiteten **Faktura**. Det här fältet hjälper till att garantera att endast de fakturor som skapas från ett avtal är synkroniserade. Värdet är **sant** om fakturan innehåller minst en fakturarad som härrör från ett avtal.

Fältet **Har rader med avtalsursprung** har lagts till i entiteten **Fakturarad**. Det här fältet hjälper till att garantera att endast de fakturarader som skapas från ett avtal är synkroniserade. Värdet är **sant** om fakturaraden kommer från ett avtal.

**Fakturadatum** är ett obligatoriskt fält i Finance and Operations. Därför måste fältet ha ett värde i Field Service innan synkroniseringen sker. Följande logik måste läggas till för att uppfylla detta krav:

- Om fältet **Fakturadatum** är tomt på entiteten **Faktura** (om den inte har något värde), anges det aktuella datumet när en fakturarad som härrör från en överenskommelse läggs till.
- Användaren kan ändra fältet **Fakturadatum**. Men när användaren försöker spara en faktura som härrör från ett avtal får han eller hon ett affärsprocessfel om fältet **Fakturadatum** är tomt på fakturan.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

### <a name="in-finance-and-operations"></a>I Finance and Operations

Ett fakturafakturaursprung måste ställas in för integrationen för att särskilja fritextfakturor i Finance and Operations som skapas från avtalsfakturor i Field Service. När en faktura har ett fakturaursprung i typen **Integration avtal/faktura** visas fältet **Externt fakturanummer** på rubriken för **Försäljningsfaktura**.

Förutom att visas på fakturarubriken, kan information **Externt fakturanummer** användas för att garantera att fakturor som skapas från avtalsfakturor för Field Service filtreras bort under synkroniseringen av fakturan från Finance and Operations till Field Service.

1. Gå till **Kundreskontra** \> **Inställningar** \> **Ursprungskoder för faktura**.
2. Välj **Ny** för att skapa ett nytt fakturaursprung.
3. I fältet **Fakturaursprung** anger du ett namn för fakturaursprung som t.ex. **FS**.
4. I fältet **Beskrivning** anger du en beskrivning såsom **Avtalsfakturor för Field Service**.
5. Markera kryssrutan **Tilldelning av ursprungstyp**.
6. Ange fältet **Typ av fakturaursprung** till **Integration avtal/faktura**.
7. Välj **Spara**.

### <a name="in-the-data-integration-project"></a>I dataintegreringsprojektet

Uppgift: **Fakturarader**  

Se till att standardvärdet för Finance and Operations-fältet **Visningsvärde för huvudkonto** uppdateras så att det matchar det önskade värdet.

Standardmallvärdet är **401100**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-headers"></a>Avtalsfakturor (Field Service till Fin and Ops): Fakturarubriker

[![Mallmappning i dataintegrering](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-lines"></a>Avtalsfakturor (Field Service till Fin and Ops): Fakturarubrikrader

[![Mallmappning i dataintegrering](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)

