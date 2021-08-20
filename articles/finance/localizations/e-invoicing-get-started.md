---
title: Kom i gång med elektronisk fakturering
description: Det här avsnittet innehåller information som hjälper dig att komma igång med elektronisk fakturering i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 3a62f68718a9bd46cdf15146bbb6a4e5166bfcc7abcf99b24d3fbc7e3e6c94ab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732991"
---
# <a name="get-started-with-electronic-invoicing"></a>Kom i gång med elektronisk fakturering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information som hjälper dig att komma igång med elektronisk fakturering. I det här avsnittet får du hjälp med de vanliga konfigurationsstegen i Regulatory Configuration Services (RCS) och Dynamics 365 Finance och tillhandahåller stegen du måste följa för att skicka in affärsdokument och granska behandlingsresultaten.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:

- Konfigurera din Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS) och din Microsoft Dynamics 365 Finance eller Dynamics 365 Supply Chain Management miljö. Mer information finns i [Kom igång med Elektronisk fakturering](e-invoicing-get-started-service-administration.md).
- Skapa en konfigurationsleverantör för organisationen. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importera en elektronisk faktureringsfunktion från Microsofts konfigurationsleverantör 

1. Logga in på ditt konto för Regelkonfigurationstjänst (RCS).
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Funktioner**, välj panelen **Elektronisk faktura**.
3. Välj **Import** och sedan **Synkronisera**.
4. Filtrera kolumnen **Konfigurationsleverantör** med termen **Microsoft**.
5. Välj namnet på en elektronisk faktureringsfunktion i tabellen i början av det här ämnet och välj sedan **Importera**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Skapa en funktion för elektronisk fakturering för organisationsleverantören

1. I RCS, avsnittet **Funktioner** i arbetsytan **Globaliseringsfunktioner**, välj panelen **Elektroniska fakturor**.
2. Välj **Lägg till** > **Baserat på befintlig funktion** innan du i fältet **Namn** anger namnet på den elektroniska faktureringsfunktionen.
3. I fältet **Beskrivning** anger du en beskrivning av funktionen.
4. I **Fältet basfunktion** väljer du den importerade funktionen för elektronisk fakturering från Microsofts konfigurationsleverantör.
5. Välj **skapa funktion**.

## <a name="country-specific-configuration-for-electronic-invoicing-feature"></a>Landsspecifik konfiguration för Elektronisk faktureringsfunktion

Beroende på land eller region kan den elektroniska faktureringsfunktionen kräva specifik konfiguration. 

Specifika steg finns i dokumentationen "Kom igång" som är tillgänglig för ditt land eller din region.

## <a name="import-the-model-mapping-configurations-from-electronic-reporting"></a>Importera modellmappningskonfigurationer från elektronisk rapportering

1. Välj arbetsytan Elektronisk rapportering i **RCS**.
2. Från listan **Microsoft** konfigurationsleverantörer, välj **Databaser**.
3. Välj **Global** och i åtgärdsfönstret genom att välja **Öppna**.
4. Importera modellmappningskonfigurationerna enligt följande tabell efter funktionsnamn.

| Funktionsnamn                         | Konfiguration och modellmappning |
|--------------------------------------|-----------------------------|
| Österrikiska elektroniska fakturor (AT)    | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Belgisk elektronisk faktura (BE)      | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Brasiliansk NF-e (BR)                  | <p>Kontextmodell för kundfaktura</p><p>Skattedokument</p><p>Modell för svarsmeddelande</p> |
| Brasiliansk NFS-e ABRASF Curitiba (BR) | <p>Kontextmodell för kundfaktura</p><p>Skattedokument</p><p>Modell för svarsmeddelande</p> |
| Dansk elektronisk faktura (DK)       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Egyptisk elektronisk faktura (EG)     | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p><p>Modell för svarsmeddelande</p> |
| Estnisk elektronisk faktura (EE)     | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Avsluta elektronisk faktura (FI)       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Fransk elektronisk faktura (FR)       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Tysk elektronisk faktura (DE)       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| FatturaPA (IT)                       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Mexikansk CFDI Interfactura (MX)       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p><p>Modell för svarsmeddelande</p> |
| Holländsk elektronisk faktura (NL)        | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Norsk elektronisk faktura (NO)    | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Spansk elektronisk faktura (ES)      | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| PEPPOL-elektronisk faktura            | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |


## <a name="configure-the-application-setup"></a>Konfigurera programmets inställningar

1. Välj den funktion för elektronisk fakturering som du har skapat.
2. På fliken **Konfigurationer** väljer du **Programkonfiguration**.
3. I fältet **Anslut program** väljer du den anslutning som är associerad med din instans av Finance eller Supply Chain Management.
4. I avsnittet **Elektroniska dokumenttyper** väljer du **Lägg till**.
5. Välj och ange ett värde för **Tabellnamn** enligt följande tabell.

    | Funktionsnamn                         | Affärsdokument | Tabellnamn |
    |--------------------------------------|-------------------|------------|
    | Österrikiska elektroniska fakturor (AT)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Belgisk elektronisk faktura (BE)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Brasiliansk NF-e (BR)                  | <p>Skattedokument</p><p>Rättelsebrev</p> | Skattedokument |
    | Brasiliansk NFS-e ABRASF Curitiba (BR) | Skattedokument för tjänster | Skattedokument |
    | Dansk elektronisk faktura (DK)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Egyptisk elektronisk faktura (EG)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Estnisk elektronisk faktura (EE)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Avsluta elektronisk faktura (FI)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Fransk elektronisk faktura (FR)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Tysk elektronisk faktura (DE)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | FatturaPA (IT)                       | <p>Försäljningsfaktura</p><p>Projektfaktura | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Mexikansk CFDI Interfactura (MX)       | <p>Försäljningsfaktura</p><p>Följesedel</p><p>Lageröverföring</p><p>Betalningskomplement</p> | Kundfakturajournal |
    | Holländsk elektronisk faktura (NL)        | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Norsk elektronisk faktura (NO)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Spansk elektronisk faktura (ES)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | PEPPOL-elektronisk faktura            | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |

7. För varje tabellnamn du skapar väljer du och anger ett kontextvärde enligt följande tabell.

    | Funktionsnamn                         | Affärsdokument | Kontext |
    |--------------------------------------|-------------------|---------|
    | Österrikiska elektroniska fakturor (AT)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Belgisk elektronisk faktura (BE)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Brasiliansk NF-e (BR)                  | <p>Skattedokument</p><p>Rättelsebrev</p> | <p>Kontextmodell för kundfaktura – kontext för skattedokument</p><p>Kontextmodell för kundfaktura – kontext för FD-korrigeringsbrev</p> |
    | Brasiliansk NFS-e ABRASF Curitiba (BR) | Skattedokument för tjänster| Kontextmodell för kundfaktura – kontext för skattedokument |
    | Dansk elektronisk faktura (DK)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Egyptisk elektronisk faktura (EG)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Estnisk elektronisk faktura (EE)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Avsluta elektronisk faktura (FI)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Fransk elektronisk faktura (FR)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Tysk elektronisk faktura (DE)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | FatturaPA (IT)                       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Mexikansk CFDI Interfactura (MX)       | <p>Försäljningsfaktura</p><p>Följesedel</p><p>Lageröverföring</p><p>Betalningskomplement</p> | Kontextmodell för kundfaktura – kontext för kundfaktura |
    | Holländsk elektronisk faktura (NL)        | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Norsk elektronisk faktura (NO)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Spansk elektronisk faktura (ES)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | PEPPOL-elektronisk faktura            | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |

8. För varje tabellnamn och sammanhang, välj och ange ett mappningsvärde för affärsdokument enligt följande tabell.

    | Funktionsnamn                         | Affärsdokument | Mappning av affärsdokument |
    |--------------------------------------|-------------------|---------------------------|
    | Österrikiska elektroniska fakturor (AT)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Belgisk elektronisk faktura (BE)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Brasiliansk NF-e (BR)                  | <p>Skattedokument</p><p>Rättelsebrev</p> | <p>Mappning av skattedokument – Mappning av skattedokument</p><p>Mappning av skattedokument – mappning av korrigeringsbrev</p> |
    | Brasiliansk NFS-e ABRASF Curitiba (BR) | Skattedokument för tjänster | Mappning av skattedokument – Mappning av skattedokument |
    | Dansk elektronisk faktura (DK)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Egyptisk elektronisk faktura (EG)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Estnisk elektronisk faktura (EE)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Avsluta elektronisk faktura (FI)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Fransk elektronisk faktura (FR)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Tysk elektronisk faktura (DE)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | FatturaPA (IT)                       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Mexikansk CFDI Interfactura (MX)       | <p>Försäljningsfaktura</p><p>Följesedel</p><p>Lageröverföring</p><p>Betalningskomplement</p> | Fakturamodellmappning – Kundfaktura |
    | Holländsk elektronisk faktura (NL)        | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Norsk elektronisk faktura (NO)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Spansk elektronisk faktura (ES)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | PEPPOL-elektronisk faktura            | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |


## <a name="country-specific-configuration-of-application-setup"></a>Landsspecifik konfiguration av programinställningar

Beroende på land eller region kan den programkonfiguration kräva specifik konfiguration. 

Specifika steg finns i dokumentationen "Kom igång" som är tillgänglig för ditt land eller din region.

## <a name="deploy-the-electronic-invoicing-feature-to-service-environment"></a>Distribuera funktionen elektronisk fakturering till tjänstemiljö

1. I fliken **Version** väljer du den version av Elektronisk fakturering som du vill distribuera.
2. Välj **Ändra status** \> **Slutför**.
3. Välj **Ändra status** \> **Publicera**.
4. Välj **Distribuera**.
5. Ställ in alternativet **Distribuera till anslutet program** som **Nej**.
6. Ställ in alternativet **Distribuera till tjänstemiljö** som **Ja**.
7. I fältet **Tjänstemiljö** väljer du den tjänstemiljö för Elektronisk fakturering där du vill distribuera funktionen Elektronisk fakturering.
8. I fältet **Från-datum** väljer du det datum då Elektronisk fakturering måste börja gälla i Elektronisk fakturering.
9. Välj **OK**.

## <a name="deploy-the-electronic-invoicing-feature-to-connected-application"></a>Distribuera funktionen elektronisk fakturering till anslutet program

1. I fliken **Version** väljer du den version av Elektronisk fakturering som du vill distribuera.
4. Välj **Distribuera**.
5. Ställ in alternativet **Distribuera till anslutet program** som **Ja**.
6. I fältet **Anslut program** väljer du den anslutning som är associerad med din instans av Finance eller Supply Chain Management.
7. Ställ in alternativet **Distribuera till tjänstemiljö** som **Nej**.
10. Välj **OK**.

## <a name="turn-on-the-electronic-invoicing-feature-in-finance-or-supply-chain-management"></a>Aktivera funktionen Elektronisk fakturering i Finance eller Supply Chain Management

1. Logga in i Finance eller Supply Chain Management och kontrollera att du befinner dig i rätt juridisk person.
2. Gå till **Organisationsadministration** \> **Inställningar** \> **Parametrar för elektroniskt dokument**.
3. På fliken **Funktioner** väljer du den lands-/regionspecifika funktionen för att aktivera funktionen Elektronisk fakturering för Finance eller Supply Chain Management. I följande tabell finns en lista över de elektroniska faktureringsfunktionerna som är tillgängliga för specifika land/regioner. 

    | Funktionsnamn                                          | Land/region  |
    |-------------------------------------------------------|-----------------|
    | Österrikiska elektroniska fakturor (AT)                     | Österrike         |
    | Belgisk elektronisk faktura (BE)                       | Belgien         |
    | CFDI Mexikansk elektronisk faktura (MX)                  | Mexiko          |
    | Dansk elektronisk faktura (DK)                        | Danmark         |
    | Holländsk elektronisk faktura (NL)                         | Nederländerna |
    | Egyptisk elektronisk faktura (EG)                      | Egypten           |
    | Estnisk elektronisk faktura (EE)                      | Estland         |
    | Finsk elektronisk faktura (FI)                       | Finland         |
    | Fransk elektronisk faktura (FR)                        | Frankrike          |
    | Tysk elektronisk faktura (DE)                        | Tyskland         |
    | Italiensk elektronisk faktura (IT)                       | Italien           |
    | NF-e Federal – brasiliansk elektronisk faktura (BR)      | Brasilien          |
    | NFS-e – brasiliansk elektronisk faktura   | Brasilien          |
    | Norsk elektronisk faktura (NO)                     | Norge          |
    | PEPPOL-elektronisk faktura                             | Globalt          |
    | Spansk elektronisk faktura (ES)                       | Spanien           |

4. Välj **Spara**.

## <a name="issue-electronic-invoices"></a>Utfärda elektroniska fakturor

1. Gå till **Organisationsadministration** \> **Periodisk** \> **Elektroniska dokument** \> **Skicka in elektroniska dokument**.
2. På snabbfliken **Post att inkludera** väljer du **Filter**.
3. Välj **Lägg till** om du vill lägga till ett registernamn i frågefiltret.
4. Välj det register som innehåller fakturorna.

    > [!NOTE]
    > Registernamnet måste finnas med i registret i avsnittet [Konfigurera programinställningar](#configure-the-application-setup) som beskrivs tidigare i detta ämne.

5. Välj det fältnamn i registret som du vill söka i.
6. Ange registrets namn och fältnamn för kriteriet som du vill söka efter.
7. Upprepa steg 5 och 6 om du vill lägga till fler fält och kriterier i frågan, och välj sedan **OK**.
8. Välj **OK**.

## <a name="view-submission-logs"></a>Visa överföringsloggar

1. Gå till **Organisationsadministration** \> **Periodisk** \> **Elektroniska dokument** \> **Inlämningslogg för elektroniska dokument**.
2. I fältet **Dokumenttyp** anger du et register som innehåller fakturorna.

    > [!NOTE]
    > Registernamnet måste finnas med i registret i avsnittet [Konfigurera programinställningar](#configure-the-application-setup) som beskrivs tidigare i detta ämne.

3. Välj en faktura u rutnätet och välj sedan **Sök** \> **Sändningsinformation**.


## <a name="related-topics"></a>Relaterade ämnen

- [Elektronisk fakturering – översikt](e-invoicing-service-overview.md)
- [Kom i gång med tjänstadministration för elektronisk fakturering](e-invoicing-get-started-service-administration.md)
- [Kom i gång med elektronisk fakturering för Brasilien](e-invoicing-bra-get-started.md)
- [Kom i gång med elektronisk fakturering för Mexiko](e-invoicing-mex-get-started.md)
- [Kom i gång med elektronisk fakturering för Italien](e-invoicing-ita-get-started.md)
- [Elektroniska kundfakturor i Egypten](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
