---
title: Kom igång med tillägget elektronisk fakturering
description: Det här avsnittet innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 07954c5c96f390bc651794f8b6c61f2a1a17ab8b
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111230"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Kom igång med tillägget elektronisk fakturering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering.

I tabellen nedan visas funktionerna för elektronisk fakturering och de affärsdokument som de kan användas för.

| Funktionsnamn                         | Affärsdokument |
|--------------------------------------|-------------------|
| Österrikiska elektroniska fakturor (AT)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| Belgisk elektronisk faktura (BE)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| Brasiliansk NF-e (BR)                  | <p>Skattedokument modell 55</p><p>Rättelsebrev</p> |
| Brasiliansk NFS-e ABRASF Curitiba (BR) | Skattedokument för tjänster |
| Brasiliansk NFS-e São Paulo (BR)       | Skattedokument för tjänster |
| Dansk elektronisk faktura (DK)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| Egyptisk elektronisk faktura (EG)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| Estnisk elektronisk faktura (EE)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| Avsluta elektronisk faktura (FI)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| Fransk elektronisk faktura (FR)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| Tysk elektronisk faktura (DE)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| FatturaPA (IT)                       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| Mexikansk CFDI Interfactura (MX)       | <p>Försäljningsfaktura</p><p>Följesedel</p><p>Lageröverföring</p><p>Betalningskomplement</p> |
| Holländsk elektronisk faktura (NL)        | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| Norsk elektronisk faktura (NO)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| Spansk elektronisk faktura (ES)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |
| PEPPOL-elektronisk faktura            | <p>Försäljningsfaktura</p><p>Projektfaktura</p> |

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:

- Konfigurera din myndighetskonfigurationstjänst (RCS) och din Microsoft Dynamics 365 Finance- eller Dynamics 365 Supply Chain Management-miljö så att du kan skicka till tillägget Elektronisk fakturering.
- Skapa en servicemiljö och publicera den i tillägget Elektronisk fakturering. Mer information finns i [Kom igång med tillägget Elektronisk fakturering](e-invoicing-get-started-service-administration.md).
- Skapa ett anslutet program. Mer information finns i [Kom igång med tillägget Elektronisk fakturering](e-invoicing-get-started-service-administration.md).
- Skapa en konfigurationsleverantör för organisationen. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importera en elektronisk faktureringsfunktion från Microsofts konfigurationsleverantör 

1. Logga in på ditt konto för Regelkonfigurationstjänst (RCS).
2. I arbetsytan **Globaliseringsfunktioner** i avsnittet **Funktioner** väljer du panelen **e-fakturering**.
3. Välj **Import** och sedan **Synkronisera**.
4. Filtrera kolumnen **Konfigurationsleverantör** med termen **Microsoft**.
5. Välj namnet på en elektronisk faktureringsfunktion i tabellen i början av det här ämnet och välj sedan **Importera**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Skapa en funktion för elektronisk fakturering för organisationsleverantören

1. I RCS, i avsnittet **Funktioner** i arbetsytan **Globaliseringsfunktion** väljer du panelen för **e-fakturering**.
2. Välj **Lägg till** > **Baserat på befintlig funktion** innan du i fältet **Namn** anger namnet på den elektroniska faktureringsfunktionen.
3. I fältet **Beskrivning** anger du en beskrivning av funktionen.
4. I **Fältet basfunktion** väljer du den importerade funktionen för elektronisk fakturering från Microsofts konfigurationsleverantör.
5. Välj **skapa funktion**.

## <a name="configure-the-electronic-invoicing-feature"></a>Konfigurera den elektroniska faktureringsfunktionen

Beroende på land eller region kan den elektroniska faktureringsfunktionen kräva ytterligare konfiguration. Specifika steg finns i dokumentationen "Kom igång" som är tillgänglig för ditt land eller din region.

## <a name="configure-the-application-setup"></a>Konfigurera programmets inställningar

1. Välj den funktion för elektronisk fakturering som du har skapat.
2. I fliken **Version** bekräftar du att versionen **Utkast** har valts.
3. På fliken **Konfigurationer** väljer du **Programkonfiguration**.

    > [!NOTE]
    > Kontrollera att din organisation är inställd som **Aktiv** konfigurationsleverantör. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva.](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

4. Välj **Funktionsinställningar** och välj sedan **Anslutet program**.
5. I avsnittet **Elektroniska dokumenttyper** väljer du **Lägg till**.
6. För varje affärsdokument som funktionen har stöd för väljer samt anger du ett **Registernamn** enligt nedanstående tabellen.

    | Funktionsnamn                         | Affärsdokument | Tabellnamn |
    |--------------------------------------|-------------------|------------|
    | Österrikiska elektroniska fakturor (AT)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Belgisk elektronisk faktura (BE)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Brasiliansk NF-e (BR)                  | <p>Skattedokument</p><p>Rättelsebrev</p> | Skattedokument |
    | Brasiliansk NFS-e ABRASF Curitiba (BR) | Skattedokument för tjänster | Skattedokument |
    | Brasiliansk NFS-e São Paulo (BR)       | Skattedokument för tjänster | Skattedokument |
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

7. För varje affärsdokument som funktionen har stöd för väljer samt anger du ett **Kontext**-värde enligt nedanstående tabell.

    | Funktionsnamn                         | Affärsdokument | Kontext |
    |--------------------------------------|-------------------|---------|
    | Österrikiska elektroniska fakturor (AT)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Belgisk elektronisk faktura (BE)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Brasiliansk NF-e (BR)                  | <p>Skattedokument</p><p>Rättelsebrev</p> | <p>Kontextmodell för kundfaktura – kontext för skattedokument</p><p>Kontextmodell för kundfaktura – kontext för FD-korrigeringsbrev</p> |
    | Brasiliansk NFS-e ABRASF Curitiba (BR) | Skattedokument för tjänster| Kontextmodell för kundfaktura – kontext för skattedokument |
    | Brasiliansk NFS-e São Paulo (BR)       | Skattedokument för tjänster| Kontextmodell för kundfaktura – kontext för skattedokument |
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

8. För varje affärsdokument som funktionen har stöd för väljer samt anger du ett **Mappning för affärsdokument**-värde enligt nedanstående tabell.

    | Funktionsnamn                         | Affärsdokument | Mappning av affärsdokument |
    |--------------------------------------|-------------------|---------------------------|
    | Österrikiska elektroniska fakturor (AT)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Belgisk elektronisk faktura (BE)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Brasiliansk NF-e (BR)                  | <p>Skattedokument</p><p>Rättelsebrev</p> | <p>Mappning av skattedokument – Mappning av skattedokument</p><p>Mappning av skattedokument – mappning av korrigeringsbrev</p> |
    | Brasiliansk NFS-e ABRASF Curitiba (BR) | Skattedokument för tjänster | Mappning av skattedokument – Mappning av skattedokument |
    | Brasiliansk NFS-e São Paulo (BR)       | Skattedokument för tjänster | Mappning av skattedokument – Mappning av skattedokument |
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

Beroende på land eller region kan den elektroniska faktureringsfunktionen kräva ytterligare konfiguration. Specifika steg finns i den "Kom igång"-dokumentation som är tillgänglig för ditt land eller din region.

## <a name="deploy-the-electronic-invoicing-feature"></a>Distribuera den elektroniska faktureringsfunktionen

1. I fliken **Version** väljer du den version av Elektronisk fakturering som du vill distribuera.
2. Välj **Ändra status** \> **Slutför**.
3. Välj **Ändra status** \> **Publicera**.
4. Välj **Distribuera**.
5. Ställ in alternativet **Distribuera till anslutet program** som **Ja**.
6. På sidan **Anslut program** väljer du den anslutning som är associerad med din instans av Finance eller Supply Chain Management.
7. Ställ in alternativet **Distribuera till tjänstemiljö** som **Ja**.
8. I fältet **Tjänstemiljö** väljer du den tjänstemiljö för tillägget Elektronisk fakturering där du vill distribuera funktionen Elektronisk fakturering.
9. I fältet **Från-datum** väljer du det datum då Elektronisk fakturering måste börja gälla i tillägget Elektronisk fakturering.
10. Välj **OK**.

## <a name="turn-on-the-electronic-invoicing-feature-in-finance-or-supply-chain-management"></a>Aktivera funktionen Elektronisk fakturering i Finance eller Supply Chain Management

1. Logga in i Finance eller Supply Chain Management och kontrollera att du befinner dig i rätt juridisk person.
2. Gå till **Organisationsadministration** \> **Inställningar** \> **Parametrar för elektroniskt dokument**.
3. På fliken **Funktioner** väljer du den/de funktionsreferens(er) som anges i följande register om du vill aktivera funktionen Elektronisk fakturering för Finance eller Supply Chain Management.

    | Funktionsnamn                         | Land/region  | Funktionsreferens |
    |--------------------------------------|-----------------|-------------------|
    | Österrikiska elektroniska fakturor (AT)    | Österrike         | EUR-00023 |
    | Belgisk elektronisk faktura (BE)      | Belgien         | EUR-00023 |
    | Brasiliansk NF-e (BR)                  | Brasilien          | BR-00053 |
    | Brasiliansk NFS-e ABRASF Curitiba (BR) | Brasilien          | BR-00095 |
    | Brasiliansk NFS-e São Paulo (BR)       | Brasilien          | BR-00095 |
    | Dansk elektronisk faktura (DK)       | Danmark         | <p>EUR-00023</p><p>DK-00001</p> |
    | Holländsk elektronisk faktura (NL)        | Nederländerna | EUR-00023 |
    | Egyptisk elektronisk faktura (EG)     | Egypten           | EG-00008 |
    | Estnisk elektronisk faktura (EE)     | Estland         | EUR-00023 |
    | Finsk elektronisk faktura (FI)      | Finland         | EUR-00023 |
     Fransk elektronisk faktura (FR)       | Frankrike           | EUR-00023 |
    | Tysk elektronisk faktura (DE)       | Tyskland         | EUR-00023 |
    | Mexikansk CFDI Interfactura (MX)       | Mexiko          | <p>MX-00010</p><p>MX-00016</p> |
    | Norsk elektronisk faktura (NO)    | Norge          | <p>EUR-00023</p><p>NO-00010</p> |
    | Spansk elektronisk faktura (ES)      | Spanien           | <p>EUR-00023</p><p>ES-00025</p> |
    | Italiensk elektronisk faktura (IT)      | Italien           | <p>EUR-00023</p><p>IT-00036</p> |
    | PEPPOL-elektronisk faktura            | Europa          | EUR-00023 |

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

Beroende på land eller region kan den elektroniska faktureringsfunktionen kräva ytterligare konfiguration. Specifika steg finns i den "Kom igång"-dokumentation som är tillgänglig för ditt land eller din region.

## <a name="related-topics"></a>Relaterade ämnen

- [Tillägg för elektronisk fakturering – översikt](e-invoicing-service-overview.md)
- [Kom igång med tillägget elektronisk fakturering för Brasilien](e-invoicing-bra-get-started.md)
- [Kom igång med tillägget elektronisk fakturering för Mexiko](e-invoicing-mex-get-started.md)
- [Kom igång med tillägget elektronisk fakturering för Italien](e-invoicing-ita-get-started.md)
- [Elektroniska kundfakturor i Egypten](emea-egy-e-invoices.md)
