---
title: Synkronisera avtalsfakturor i Field Service till fritextfakturor i Supply Chain Management
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera avtalsfakturor i Dynamics 365 Field Service till fritextfakturor i Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: f3066741781bd9058e09d7f577a35df4c9b453d4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819218"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a>Synkronisera avtalsfakturor i Field Service till fritextfakturor i Supply Chain Management

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera avtalsfakturor i Dynamics 365 Field Service till fritextfakturor i Dynamics 365 Supply Chain Management.

## <a name="templates-and-tasks"></a>Mallar och uppgifter

Följande mall och underliggande uppgifter används för att köra synkronisering av avtalsfakturor från Field Service till fritextfakturor i Supply Chain Management.

**Namnet på mallen i dataintegreringen**

- Avtalsfakturor (Field Service till Supply Chain Management)

**Namnen på uppgifterna i dataintegreringsprojektet**

- Fakturarubriker
- Fakturarader

Följande synkroniseringsuppgifter krävs före synkronisering av avtalsfakturor kan uppstå:

- Konton (Sales till Supply Chain Management) – Direkt

## <a name="entity-set"></a>Ange entiteten

| Field Service  | Hantering av underleverantörer                 |
|----------------|----------------------------------------|
| fakturor       | Dataverse fakturahuvuden i fritext för kund |
| fakturainformation | Dataverse fakturarader i fritext för kund   |

## <a name="entity-flow"></a>Flöde för entitet

Fakturor som har skapats från ett avtal i Field Service kan synkroniseras till Supply Chain Management via ett Microsoft Dataverse dataintegreringsprojekt. Uppdateringar till dessa fakturor synkroniseras till fritextfakturor i Supply Chain Management om redovisningsstatus för fritextfakturor är **pågående**. Efter fritextfakturorna bokförs i Supply Chain Management och redovisningsstatus uppdateras till **slutförd**, kan du inte längre synkronisera uppdateringar från Field Service.

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service

Kolumnen **Har rader med avtalsursprung** har lagts till i tabellen **Faktura**. Den här kolumnen hjälper till att garantera att endast de fakturor som skapas från ett avtal är synkroniserade. Värdet är **sant** om fakturan innehåller minst en fakturarad som härrör från ett avtal.

Kolumnen **Har avtalsursprung** har lagts till i tabellen **Fakturarad**. Den här kolumnen hjälper till att garantera att endast de fakturarader som skapas från ett avtal är synkroniserade. Värdet är **sant** om fakturaraden kommer från ett avtal.

**Fakturadatum** är ett obligatoriskt fält i Supply Chain Management. Därför måste kolumnen ha ett värde i Field Service innan synkroniseringen sker. Följande logik måste läggas till för att uppfylla detta krav:

- Om kolumnen **Fakturadatum** är tomt på tabellen **Faktura** (om den inte har något värde), anges det aktuella datumet när en fakturarad som härrör från en överenskommelse läggs till.
- Användaren kan ändra kolumnen **Fakturadatum**. Men när användaren försöker spara en faktura som härrör från ett avtal får han eller hon ett affärsprocessfel om kolumnen **Fakturadatum** är tomt på fakturan.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

### <a name="in-supply-chain-management"></a>I Supply Chain Management

Ett fakturafakturaursprung måste ställas in för integrationen för att särskilja fritextfakturor i Supply Chain Management som skapas från avtalsfakturor i Field Service. När en faktura har ett fakturaursprung i typen **Integration avtal/faktura** visas fältet **Externt fakturanummer** på rubriken för **Försäljningsfaktura**.

Förutom att visas på fakturarubriken, kan information **Externt fakturanummer** användas för att garantera att fakturor som skapas från avtalsfakturor för Field Service filtreras bort under synkroniseringen av fakturan från Supply Chain Management till Field Service.

1. Gå till **Kundreskontra** \> **Inställningar** \> **Ursprungskoder för faktura**.
2. Välj **Ny** för att skapa ett nytt fakturaursprung.
3. I fältet **Fakturaursprung** anger du ett namn för fakturaursprung som t.ex. **FS**.
4. I fältet **Beskrivning** anger du en beskrivning såsom **Avtalsfakturor för Field Service**.
5. Markera kryssrutan **Tilldelning av ursprungstyp**.
6. Ange fältet **Typ av fakturaursprung** till **Integration avtal/faktura**.
7. Välj **Spara**.

### <a name="in-the-data-integration-project"></a>I dataintegreringsprojektet

Uppgift: **Fakturarader**  

Se till att standardvärdet för Supply Chain Management-fältet **Visningsvärde för huvudkonto** uppdateras så att det matchar det önskade värdet.

Standardmallvärdet är **401100**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas en mallmappning i dataintegrering.

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a>Avtalsfakturor (Field Service till Supply Chain Management): Fakturarubriker

[![Mallmappning i dataintegrering](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a>Avtalsfakturor (Field Service till Supply Chain Management): Fakturarader

[![Mallmappning i dataintegrering](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]