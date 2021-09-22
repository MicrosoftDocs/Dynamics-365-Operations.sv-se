---
title: Elektroniska meddelanden
description: Det här avsnittet innehåller information om översikt och inställningar för elektronisk post i Microsoft Dynamics 365 Finance.
author: liza-golub
ms.date: 08/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 16b0e0fa74109f1c63ed47606bebe2fefc604fc5
ms.sourcegitcommit: efcb853a68a77037cca23582d9f6f96ea573727a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7478734"
---
# <a name="electronic-messaging"></a>Elektroniska meddelanden

[!include [banner](../includes/banner.md)]

I detta ämne finns en översikt samt konfigurationsinformation rörande funktionen **Elektroniska meddelanden** (EM).

Myndigheter och rättsliga myndigheter i olika länder och regioner i världen har nyligen implementerat rapporteringskraven för företag som är registrerade i dessa länder eller regioner. Syftet med kraven är att tillåta hämta data från dessa företag i elektroniskt format direkt från systemen där den bokfördes, lagrades och bearbetades.

Funktionen för elektroniska meddelanden (EM) i Microsoft Dynamics 365 Finance stöder olika processer för elektronisk driftskompatibilitet mellan Finance och de system som myndigheter och rättsliga myndigheter erbjuder för rapportering, avsändning och mottagande av officiell information.

EM-funktionen ingår i modulen **Elektronisk rapportering** (ER). Du kan konfigurera ER-format för elektroniska meddelanden. Mer information finns i [Elektronisk rapportering (ER)](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

## <a name="basic-concepts-for-em-functionality"></a>Grundläggande koncept för EM-funktioner

EM-funktionerna baseras på följande entiteter:

- **Elektroniskt meddelande** – En rapport eller deklaration som ska rapporteras eller överföras internt, till exempel en rapport som skickas till ett skattekontor.
- **Elektroniska meddelandeartiklar** – poster som ska tas med i meddelandet som rapporteras.
- **Elektronisk meddelandebearbetning** – en åtgärdskedja som bör köras för att samla in nödvändiga uppgifter, generera rapporter, lagra data i Azure Blob Storage, överföra rapporter från utanför systemet, få svar från utanför systemet samt uppdatera databasen baserat på den information som tas emot. Åtgärderna i kedjan kan vara länkade eller inte länkade.

Illustrationen som följer visar dataflödet för EM.

![Dataflöde i elektroniska meddelanden.](media/electronic-messaging-data-flow.png)

## <a name="scenarios-supported-by-the-em-functionality"></a>Scenarier som stöds av EM-funktionerna

EM-funktionen stöder följande scenarier:

- Skapa meddelanden manuellt och generera rapporter utifrån associerade ER-exportformat av olika slag. Dessa typer inkluderar Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, text och Microsoft Word.
- Skapa och bearbeta meddelanden automatiskt som baseras på information som har begärts och erhållits från en utfärdare via ett associerat ER-importformat.
- Samla in och bearbeta information från en datakälla som meddelandeartiklar. Datakällan är en Finance-tabell.
- Lagra ytterligare information och utvärdera olika värden genom att uttryckligen anropa definierade körbara klasser i förhållande till meddelanden eller meddelandeartiklar.
- Sätta samman information som samlas in i en meddelandeartikel, dela upp den informationen per meddelande och generera rapporter med tillhörande ER-exportformat.
- Skicka rapporter som genererats till en webbtjänst med hjälp av säkerhetsinformation som lagras i Azure-nyckelvalvet.
- Få ett svar från en webbtjänst, tolka svaret och uppdatera data i Finance enligt önskemål.
- Spara och granska alla rapporter som skapas.
- Spara och granska all logginformation som är relaterad till åtgärder som körs för ett meddelande eller en meddelandeartikel.
- Kontrollera bearbetning genom olika meddelandestatus och status för meddelandeartikel.

## <a name="security-privileges"></a>Säkerhetsprivilegier

Följande säkerhetsprivilegier är tillgängliga för elektroniska meddelanden.

| Säkerhetsprivilegium           | Åtkomstnivå | Koppling |
|------------------------------|--------------|-------------|
| Underhåll elektroniska meddelanden | Det här privilegiet ger fullständig åtkomst till EM-funktionerna. Om du har det här privilegiet kan du konfigurera elektroniska meddelanden och köra all bearbetning. | Detta privilegium ingår i säkerhetsuppdraget **Underhålla momstransaktioner**. Detta uppdrag ingår i sin tur i säkerhetsrollen **Redovisare**. |
| Visa elektroniska meddelanden     | Det här privilegiet ger skrivskyddad åtkomst till EM-funktionerna. Om du har det här privilegiet kan du visa inställningar för elektroniska meddelanden och själva meddelandena. Du kan däremot inte konfigurera eller köra något. | Detta privilegium ingår i säkerhetsuppdraget **Fråga om momstransaktionsstatus**. Detta uppdrag ingår i sin tur i följande säkerhetsroller:<ul><li>Inkassochef</li><li>Kundreskontraansvarig</li><li>Kundreskontrachef</li><li>Skatteredovisare</li><li>Redovisare</li><li>Redovisningschef</li><li>Redovisningsansvarig</li><li>Försäljningschef</li><li>Leverantörsreskontraansvarig</li></ul> |
| Arbeta med elektroniska meddelanden  | Detta privilegium ger bara åtkomst till sidorna **Elektroniska meddelanden** och **Elektroniska meddelandeartiklar**. Om du har det här privilegiet kan du köra all bearbetning som anropas från dessa sidor. | Detta privilegium ingår i säkerhetsuppdraget **Hantera elektroniska meddelanden**. Detta uppdrag ingår i sin tur i säkerhetsrollen **Operatör för elektroniska meddelanden**. |

## <a name="country-specific-regulatory-features-supported-by-the-em-functionality"></a>Landsspecifika lagstadgade funktioner som stöds av EM-funktionerna

Följande tabell innehåller information om vissa landsspecifika regleringsfunktioner som stöds av EM-funktionerna.

| Land     | Funktionsnamn | Funktionsdemoregistrering |
|-------------|--------------|------------------------|
| Spanien       | [Omedelbar leverans av information om moms (Suministro Inmediato de Información del IVA, SII)](../localizations/emea-esp-sii.md) | |
| Ungern     | [Faktureringssystem online](../localizations/emea-hun-online-invoicing.md) | |
| Storbritannien | [Making Tax Digital (MTD) – skicka in momsutlåtande](../localizations/emea-gbr-mtd-vat-integration.md) | [Finance and Operations: UK Digital Tax - Momsdeklaration i Dynamics 365](https://community.dynamics.com/365/b/techtalks/posts/finance-and-operations-uk-digital-tax-vat-declaration-in-dynamics-365) |
| Litauen   | [i.SAF-rapportering](../localizations/emea-ltu-isaf.md) | |
| Polen      | [Momsdeklaration med kassaapparater (JPK_V7M, VDEK)](../localizations/emea-pol-vdek.md) | [Dynamics 365 Finance: SAF/JPK-momsrevisionsregister](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-finance-saf-jpk-vat-audit-registers-june-4-2020) |
| Nederländerna | [Momsdeklaration för Nederländerna](../localizations/emea-nl-vat-declaration-netherlands.md) | |
| Tjeckien | [Momsdeklaration](../localizations/emea-cze-vat-declaration-tax-declaration-model.md) | |
| Brasilien      | [SPED-Reinf](../localizations/latam-bra-sped-reinf-overview.md) | |
| Ryssland      | [Momsdeklaration](../localizations/rus-vat-declaration.md) | |
| Ryssland      | [Redovisningsrapportering i elektroniskt format](../localizations/rus-accounting-reporting.md) | |
| Ryssland      | [Vinstskattdeklaration](../localizations/rus-profit-tax-declaration.md) | |
| Ryssland      | [Preliminär momsdeklaration](../localizations/rus-assessed-tax-declaration.md) | |
| Ryssland      | [Momsdeklaration för transport](../localizations/rus-transport-tax-declaration.md) | |
| Ryssland      | [Deklaration för markvärdesmoms](../localizations/rus-land-tax-declaration.md) | |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

