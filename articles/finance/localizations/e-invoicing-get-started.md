---
title: Kom i gång med e-fakturering
description: Det här avsnittet innehåller information som hjälper dig att komma igång med e-fakturering i Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 11/08/2021
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
ms.openlocfilehash: ebef9cf97f7a91e0a2fd45f5e0e0fc620070b42a
ms.sourcegitcommit: 5033d42a2aac852916d726e40bd98a164d1a837d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/23/2022
ms.locfileid: "7983883"
---
# <a name="get-started-with-electronic-invoicing"></a>Kom i gång med e-fakturering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information som hjälper dig att komma igång med e-fakturering. I det här avsnittet får du hjälp med de vanliga konfigurationsstegen i Regulatory Configuration Services (RCS) och Dynamics 365 Finance och tillhandahåller stegen du måste följa för att skicka in affärsdokument och granska behandlingsresultaten.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:

- Konfigurera din Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS) och din Microsoft Dynamics 365 Finance eller Dynamics 365 Supply Chain Management miljö. Mer information finns i [Kom igång med e-fakturering](e-invoicing-get-started-service-administration.md).
- Skapa en konfigurationsleverantör för organisationen. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importera en e-faktureringsfunktion från Microsofts konfigurationsleverantör 

1. Logga in på ditt konto för Regelkonfigurationstjänst (RCS).
2. I arbetsytan **globaliseringsfunktioner** i avsnittet **Funktioner**, välj panelen **e-faktura**.
3. Välj **Import** och sedan **Synkronisera**.
4. Filtrera kolumnen **Konfigurationsleverantör** med termen **Microsoft**.
5. Välj namnet på en e-faktureringsfunktion från tabellen och välj **Importera**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Skapa en funktion för e-fakturering för organisationsprovidern

1. I RCS, avsnittet **Funktioner** i arbetsytan **Globaliseringsfunktioner**, välj panelen **e-fakturor**.
2. Välj **Lägg till** > **Baserat på befintlig funktion** innan du i fältet **Namn** anger namnet på e-faktureringsfunktionen.
3. I fältet **Beskrivning** anger du en beskrivning av funktionen.
4. I **Fältet basfunktion** väljer du den importerade funktionen för e-fakturering från Microsofts konfigurationsleverantör.
5. Välj **skapa funktion**.

## <a name="country-specific-configuration-for-electronic-invoicing-feature"></a>Landsspecifik konfiguration för e-faktureringsfunktion

Beroende på land eller region kan e-faktureringsfunktionen kräva specifik konfiguration. 

> [!NOTE]
> När du aktiverar funktionen e-fakturering för Finland stöds innte applikationsspecifika parametrar i sökningar. För att komma runt detta problem granskar du konfigurationerna för format för försäljningsfaktura och projektfaktura i modulen **Elektronisk rapportering**. Konfigurera beräknat fält för **$PaymentMethodSubstitution**-mappningen manuellt och bind sedan det fältet till fältet **EpiPaymentMeansCode** från formaten för försäljningsfaktura och projektfaktura.
>
> När du aktiverar funktionen e-fakturering för Italien stöds inte applikationsspecifika parametrar i sökningar. För att komma runt detta problem öppnar du modulen **Elektronisk rapportering** och konfigurerar beräknat fät för mappningen **$NaturaReverseCharge** manuellt.
>
> Specifika steg relaterade till andra platser finns i dokumentationen "Kom igång" som är tillgänglig för ditt land eller din region.

## <a name="import-the-model-mapping-configurations-from-electronic-reporting"></a>Importera modellmappningskonfigurationer från elektronisk rapportering

1. Välj arbetsytan Elektronisk rapportering i **RCS**.
2. Från listan **Microsoft** konfigurationsleverantörer, välj **Databaser**.
3. Välj **Global** och i åtgärdsfönstret genom att välja **Öppna**.
4. Importera modellmappningskonfigurationerna enligt följande tabell efter funktionsnamn.

| Funktionsnamn                         | Konfiguration och modellmappning |
|--------------------------------------|-----------------------------|
| Österrikiska e-fakturor (AT)    | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Belgisk e-faktura (BE)      | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Brasiliansk NF-e (BR)                  | <p>Kontextmodell för kundfaktura</p><p>Skattedokument</p><p>Modell för svarsmeddelande</p> |
| Brasiliansk NFS-e ABRASF Curitiba (BR) | <p>Kontextmodell för kundfaktura</p><p>Skattedokument</p><p>Modell för svarsmeddelande</p> |
| Dansk e-faktura (DK)       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Egyptisk e-faktura (EG)     | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p><p>Modell för svarsmeddelande</p> |
| Estnisk e-faktura (EE)     | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Avsluta e-faktura (FI)       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Fransk e-faktura (FR)       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Tysk e-faktura (DE)       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| FatturaPA (IT)                       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Mexikansk CFDI Interfactura (MX)       | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p><p>Modell för svarsmeddelande</p> |
| Holländsk e-faktura (NL)        | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Norsk e-faktura (NO)    | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| Spansk e-faktura (ES)      | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| PEPPOL-e-faktura            | <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |
| e-faktura för Saudiarabien (SA)| <p>Kontextmodell för kundfaktura</p><p>Fakturamodell</p> |


## <a name="configure-the-application-setup"></a>Konfigurera programmets inställningar

1. Välj den funktion för e-fakturering som du har skapat.
2. På fliken **Konfigurationer** väljer du **Programkonfiguration**.
3. I fältet **Anslut program** väljer du den anslutning som är associerad med din instans av Finance eller Supply Chain Management.
4. I avsnittet **Elektroniska dokumenttyper** väljer du **Lägg till**.
5. Välj och ange ett värde för **Tabellnamn** enligt följande tabell.

    | Funktionsnamn                         | Affärsdokument | Tabellnamn |
    |--------------------------------------|-------------------|------------|
    | Österrikiska e-fakturor (AT)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Belgisk e-faktura (BE)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Brasiliansk NF-e (BR)                  | <p>Skattedokument</p><p>Rättelsebrev</p> | Skattedokument |
    | Brasiliansk NFS-e ABRASF Curitiba (BR) | Skattedokument för tjänster | Skattedokument |
    | Dansk e-faktura (DK)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Egyptisk e-faktura (EG)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Estnisk e-faktura (EE)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Avsluta e-faktura (FI)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Fransk e-faktura (FR)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Tysk e-faktura (DE)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | FatturaPA (IT)                       | <p>Försäljningsfaktura</p><p>Projektfaktura | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Mexikansk CFDI Interfactura (MX)       | <p>Försäljningsfaktura</p><p>Följesedel</p><p>Lageröverföring</p><p>Betalningskomplement</p> | Kundfakturajournal |
    | Holländsk e-faktura (NL)        | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Norsk e-faktura (NO)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | Spansk e-faktura (ES)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | PEPPOL-e-faktura            | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |
    | e-faktura för Saudiarabien (SA)| <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kundfakturajournal</p><p>Projektfaktura</p> |

6. För varje tabellnamn du skapar väljer du och anger ett kontextvärde enligt följande tabell.

    | Funktionsnamn                         | Affärsdokument | Kontext |
    |--------------------------------------|-------------------|---------|
    | Österrikiska e-fakturor (AT)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Belgisk e-faktura (BE)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Brasiliansk NF-e (BR)                  | <p>Skattedokument</p><p>Rättelsebrev</p> | <p>Kontextmodell för kundfaktura – kontext för skattedokument</p><p>Kontextmodell för kundfaktura – kontext för FD-korrigeringsbrev</p> |
    | Brasiliansk NFS-e ABRASF Curitiba (BR) | Skattedokument för tjänster| Kontextmodell för kundfaktura – kontext för skattedokument |
    | Dansk e-faktura (DK)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Egyptisk e-faktura (EG)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Estnisk e-faktura (EE)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Avsluta e-faktura (FI)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Fransk e-faktura (FR)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Tysk e-faktura (DE)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | FatturaPA (IT)                       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Mexikansk CFDI Interfactura (MX)       | <p>Försäljningsfaktura</p><p>Följesedel</p><p>Lageröverföring</p><p>Betalningskomplement</p> | Kontextmodell för kundfaktura – kontext för kundfaktura |
    | Holländsk e-faktura (NL)        | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Norsk e-faktura (NO)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | Spansk e-faktura (ES)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | PEPPOL-e-faktura            | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |
    | e-faktura för Saudiarabien (SA)| <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Kontextmodell för kundfaktura – kontext för kundfaktura</p><p>Kontextmodell för kundfaktura – kontext för projektfaktura</p> |

7. För varje tabellnamn och sammanhang, välj och ange ett mappningsvärde för affärsdokument enligt följande tabell.

    | Funktionsnamn                         | Affärsdokument | Mappning av affärsdokument |
    |--------------------------------------|-------------------|---------------------------|
    | Österrikiska e-fakturor (AT)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Belgisk e-faktura (BE)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Brasiliansk NF-e (BR)                  | <p>Skattedokument</p><p>Rättelsebrev</p> | <p>Mappning av skattedokument – Mappning av skattedokument</p><p>Mappning av skattedokument – mappning av korrigeringsbrev</p> |
    | Brasiliansk NFS-e ABRASF Curitiba (BR) | Skattedokument för tjänster | Mappning av skattedokument – Mappning av skattedokument |
    | Dansk e-faktura (DK)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Egyptisk e-faktura (EG)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Estnisk e-faktura (EE)     | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Avsluta e-faktura (FI)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Fransk e-faktura (FR)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Tysk e-faktura (DE)       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | FatturaPA (IT)                       | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Mexikansk CFDI Interfactura (MX)       | <p>Försäljningsfaktura</p><p>Följesedel</p><p>Lageröverföring</p><p>Betalningskomplement</p> | Fakturamodellmappning – Kundfaktura |
    | Holländsk e-faktura (NL)        | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Norsk e-faktura (NO)    | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | Spansk e-faktura (ES)      | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | PEPPOL-e-faktura            | <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |
    | e-faktura för Saudiarabien (SA)| <p>Försäljningsfaktura</p><p>Projektfaktura</p> | <p>Fakturamodellmappning – Kundfaktura</p><p>Fakturamodellmappning – Projektfaktura</p> |


## <a name="country-specific-configuration-of-application-setup"></a>Landsspecifik konfiguration av programinställningar

Beroende på land eller region kan den programkonfiguration kräva specifik konfiguration. 

Specifika steg finns i dokumentationen "Kom igång" som är tillgänglig för ditt land eller din region.

## <a name="deploy-the-electronic-invoicing-feature-to-service-environment"></a>Distribuera funktionen e-fakturering till tjänstemiljö

1. I fliken **Version** väljer du den version av e-fakturering som du vill distribuera.
2. Välj **Ändra status** \> **Slutför**.
3. Välj **Ändra status** \> **Publicera**.
4. Välj **Distribuera**.
5. Ställ in alternativet **Distribuera till anslutet program** som **Nej**.
6. Ställ in alternativet **Distribuera till tjänstemiljö** som **Ja**.
7. I fältet **Tjänstemiljö** väljer du den tjänstemiljö för e-fakturering där du vill distribuera funktionen e-fakturering.
8. I fältet **Från-datum** väljer du det datum då e-fakturering måste börja gälla i e-fakturering.
9. Välj **OK**.

## <a name="deploy-the-electronic-invoicing-feature-to-connected-application"></a>Distribuera funktionen e-fakturering till anslutet program

1. I fliken **Version** väljer du den version av e-fakturering som du vill distribuera.
2. Välj **Distribuera**.
3. Ställ in alternativet **Distribuera till anslutet program** som **Ja**.
4. I fältet **Anslut program** väljer du den anslutning som är associerad med din instans av Finance eller Supply Chain Management.
5. Ställ in alternativet **Distribuera till tjänstemiljö** som **Nej**.
6. Välj **OK**.

## <a name="turn-on-the-electronic-invoicing-feature-in-finance-or-supply-chain-management"></a>Aktivera funktionen e-fakturering i Finance eller Supply Chain Management

1. Logga in i Finance eller Supply Chain Management och kontrollera att du befinner dig i rätt juridisk person.
2. Gå till **Organisationsadministration** \> **Inställningar** \> **Parametrar för elektroniskt dokument**.
3. På fliken **Funktioner** väljer du den lands-/regionspecifika funktionen för att aktivera funktionen e-fakturering för Finance eller Supply Chain Management. I följande tabell finns en lista över de e-faktureringsfunktionerna som är tillgängliga för specifika land/regioner. 

    | Funktionsnamn                                          | Land/region  |
    |-------------------------------------------------------|-----------------|
    | Österrikiska e-fakturor (AT)                     | Österrike         |
    | Belgisk e-faktura (BE)                       | Belgien         |
    | CFDI Mexikansk e-faktura (MX)                  | Mexiko          |
    | Dansk e-faktura (DK)                        | Danmark         |
    | Holländsk e-faktura (NL)                         | Nederländerna |
    | Egyptisk e-faktura (EG)                      | Egypten           |
    | Estnisk e-faktura (EE)                      | Estland         |
    | Finsk e-faktura (FI)                       | Finland         |
    | Fransk e-faktura (FR)                        | Frankrike          |
    | Tysk e-faktura (DE)                        | Tyskland         |
    | Italiensk e-faktura (IT)                       | Italien           |
    | NF-e Federal – brasiliansk e-faktura (BR)      | Brasilien          |
    | NFS-e – brasiliansk e-faktura   | Brasilien          |
    | Norsk e-faktura (NO)                     | Norge          |
    | PEPPOL-e-faktura                             | Globalt          |
    | Spansk e-faktura (ES)                       | Spanien           |
    | e-faktura för Saudiarabien (SA)                 | Saudiarabien    |
    

4. Välj **Spara**.

## <a name="issue-electronic-invoices"></a>Utfärda e-fakturor

1. Gå till **Organisationsadministration** \> **Periodisk** \> **Elektroniska dokument** \> **Skicka in elektroniska dokument**.
2. På snabbfliken **Poster att inkludera**, välj **Filter**.
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

## <a name="download-an-electronic-document-file"></a>Ladda ned en elektronisk dokumentfil

1. Gå till **Organisationsadministration** \> **Periodisk** \> **Elektroniska dokument** \> **Inlämningslogg för elektroniska dokument**.
2. I fältet **Dokumenttyp** anger du et register som innehåller fakturorna.
3. Välj ett dokument i rutnätet och välj sedan **Elektroniskt dokument** \> **Ladda ned fil**. Ett arkiv som innehåller den elektroniska dokumentfilen kommer att föreslås för hämtning.

> [!NOTE]
> Innan du kan hämta filer måste alternativet **Exportera resultat** vara aktiverat för den relaterade åtgärden i inställningarna för e-fakturering i RCS.

## <a name="related-topics"></a>Relaterade ämnen

- [E-fakturering – översikt](e-invoicing-service-overview.md)
- [Kom i gång med tjänstadministration för e-fakturering](e-invoicing-get-started-service-administration.md)
- [Kom i gång med e-fakturering för Brasilien](e-invoicing-bra-get-started.md)
- [Kom i gång med e-fakturering för Mexiko](e-invoicing-mex-get-started.md)
- [Kom i gång med e-fakturering för Italien](e-invoicing-ita-get-started.md)
- [Elektroniska kundfakturor i Egypten](emea-egy-e-invoices.md)
- [Elektroniska kundfakturor i Saudiarabien](emea-sau-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
