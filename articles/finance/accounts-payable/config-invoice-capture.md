---
title: Konfigurera lösningen för Invoice Capture
description: I den här artikeln förklaras hur du konfigurerar lösningen Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: e297dafc930368f14f2e68213ce4153ba792ef4d
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691186"
---
# <a name="configure-the-invoice-capture-solution"></a>Konfigurera lösningen för Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

När lösningen Invoice Capture har installerats måste du konfigurera miljön. Processen består av följande grundläggande steg.

1. **Nödvändig:** Synkronisera de juridiska personerna från Microsoft Dynamics 365 Finance. Detta steg används för att ställa in organisationsstrukturen i Microsoft Power Platform.
2. **Nödvändig:** Konfigurera kanaler för import av fakturabilder. Lösningen stöder följande kanaler:

    - Office 365 Outlook (standard)
    - Outlook.com
    - OneDrive
    - SharePoint

3. **Valfritt:** Definiera ytterligare konfigurationsgrupper för OCR-tjänsten (optisk teckenläsning).
4. **Valfritt:** Definiera mappningsregler för den juridiska personen, leverantörskontot, artikeln och anskaffningstypen.

Den här artikeln fokuserar på de två nödvändiga stegen i processen. Mer information om konfigurationsgrupper finns i [Konfigurationsgrupper för lösning för Invoice Capture](invoice-capture-config-group.md). Mer information om mappningsregler finns i [mappningsregler för lösningen Invoice Capture](invoice-capture-mapping-rules.md).

## <a name="manage-legal-entities"></a>Hantera juridiska personer

Ekonomi definierar juridiska personer som organisationer som identifieras genom registrering hos juridiska myndigheter. Affärsaktiviteter utförs och registreras i separata juridiska personer. I Microsoft Power Platform är affärsenheter, säkerhetsroller och användare kopplade till varandra på ett sätt som överensstämmer med den rollbaserade säkerhetsmodellen.

Affärsenheter används tillsammans med säkerhetsroller för att kontrollera dataåtkomst. Användarna ser bara den information som de behöver för att kunna göra sina jobb. Lösningen Invoice Capture av faktura ger ett konfigurationsutrymme där du kan läsa in grundläggande information från befintliga juridiska personer i Ekonomi och hantera de enheter som skapas manuellt. De juridiska personerna används på leverantörsfakturor och i säkerhetskontroll.

När en juridisk person skapas och visas i listvyn skapas automatiskt en standardenhet som har samma namn. Teamet tilldelas säkerhetsrollen **ansvarig för leverantörsreskontra**. När juridiska personer importeras importeras grundläggande huvuddata från Ekonomi. De artiklar som inte finns identifieras av en juridisk person och lägger till dem i lösningen Invoice Capture. Standardkonfigurationsgruppen tilldelas nya juridiska personer.

### <a name="sync-legal-entities"></a>Synkronisera juridiska personer

Du kan inte skapa juridiska personer direkt. Du kan emellertid synkronisera juridiska personer från Ekonomi. Synkronisera juridiska personer genom att följa dessa steg.

1. Gå till **Inställningar \> Systeminställningar \> Hantera juridiska personer**.
2. Välj **Synkronisera juridiska personer** och välj **OK** i dialogrutan konfirmation.

När synkroniseringen har slutförts visas antalet nya juridiska personer. De nya juridiska personerna visas i listvyn. Standardkonfigurationsgruppen tilldelas nya juridiska personer.

## <a name="configure-invoice-import-channels"></a>Konfigurera fakturaimportkanaler

Leverantörer skickar fakturor från olika kanaler (e-post, filarbetsytan eller fakturaportalen) via olika format (papper eller bild). Med lösningen Invoice Capture kan du hantera olika kanaler och format. Följande typer stöds:

- Office 365 Outlook
- Outlook.com
- SharePoint
- OneDrive

När en kanal skapas för ett visst konto skapas ett automatiskt flöde med en fördefinierad mall för övervakning av inkommande e-postmeddelanden eller filer i Inkorgen eller utrymmet. Alla filer som har en giltig faktura kan identifieras och skickas till fakturaområdet och väntar på att bearbetas av leverantörsreskontra (AP). Bilagan ska vara i PDF-format eller bildformat. Fakturor kan läsas in i lösningen för Invoice Capture enligt kanalkonfigurationen.

### <a name="create-a-channel"></a>Skapa en kanal

Om du har importerat ytterligare lösningspaket (Dynamics 365 Invoice Capture – Installationsverktyg) är standardanslutningen för Office 365 Outlook klar att användas. Om du vill skapa fler anslutningar för olika e-postkonton eller andra kanaltyper finns i [Skapa ytterligare anslutningar för kanaler](invoice-capture-advanced-settings.md#create-additional-connections-for-channels).

Gör så här om du vill skapa en kanal.

1. Gå till **Inställningar \> Systeminställningar \> Konfigurera kanaler**.
2. Välj **Ny**.
3. Ange följande fält.

    - Kanalnamn
    - Beskrivning
    - Typ
    - Anslutning

Det är endast e-postmeddelanden eller filer som matchar följande kriterier som kan importeras till lösningen.

| Typ               | Konfiguration  | Mer information |
|--------------------|----------------|------------------|
| Office 365 Outlook | Mapp         | E-postmappen måste finnas under rotkatalogen. Som standard används mappen Inkorg. En undermapp stöds inte. |
|                    | Ämnesfilter | (Valfritt) Ett delsträng som ska inkluderas i ämnet. |
|                    | Från           | (Valfritt) E-postadressen till avsändaren eller avsändarna. Om du anger flera adresser, använd semikolon (;) som avgränsare. |
| SharePoint         | Webbplatsadress   | Webbadressen till webbplatsens adress. |
|                    | Mapp         | Mappen i webbadressen. |

### <a name="activate-the-channel"></a>Aktivera kanalen

När ett flöde sparas visar fälten status för kanalen och tiden när det skapades. Inledningsvis anges fältet **Status** ställs in som **Inaktiv**. Fältet **Statusorsak** indikerar att kanalen har initierats och är klar att aktiveras.

Aktivera kanalen genom att välja **Aktivera**. Fälten **Status** och **Statusorsak** uppdateras.

Om en kanal inte krävs kan du inaktivera den. Inaktivera kanalen genom att välja **Inaktivera**. Fälten **Status** och **Statusorsak** uppdateras.

### <a name="manage-flows-in-flow-management"></a>Hantera flöden i flödeshantering

Du kan visa en kanal på sidan **Konfigurera kanaler** eller i flödeshantering.

Om du vill visa mer information går du till **Administrationssystem \> Standardlösning \> Molnflöden** och väljer målflödet. I informationen som visas finns kopplade anslutningar, ägare och kör.

Om du vill synkronisera statusen väljer du **Kontrollera** för att bekräfta att kanalens status matchar flödets status.

Vissa fall av undantagshantering visas i fältet **Statusorsak**:

- **Saknar Dataverse anslutning** – Den aktuella användaren har inte skapat minst en anslutningsreferens **Microsoft Dataverse**.
- **Hittade inte** – Flödet som är länkat till kanalen har tagits bort i flödeshanteringen. Kanalen bör sparas igen för att en ny kanal ska skapas.
- **Inaktiverad i flödeshantering** – Flödet har inaktiverats i flödeshanteringen och kanalens status skiljer sig från flödets status.
- **Aktiverad i flödeshantering** – Flödet har aktiverats i flödeshanteringen och kanalens status skiljer sig från flödets status.
- **Ett oväntat fel** – Användaren måste bekräfta att webbplatsen är en "Kommunikationsplats" och att mappen är "Dokumentbibliotek".
