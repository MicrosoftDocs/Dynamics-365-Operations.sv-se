---
title: Hantering av affärsdokument – översikt
description: Den här artikeln innehåller information om hur du använder funktionen för hantering av affärsdokument i ER-ramverket.
author: kfend
ms.date: 04/23/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.assetid: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERSecurityAccessEditor
ms.openlocfilehash: 0fab7e1a36d9b4092cf4353533704859e83bed26
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288301"
---
# <a name="business-document-management-overview"></a>Översikt över hantering av affärsdokument

[!include [banner](../includes/banner.md)]

Affärsanvändare använder ramverket [elektronisk rapportering (ER)](general-electronic-reporting.md) för att konfigurera format för utgående dokument i enlighet med lagkraven för olika länder/regioner. Användare kan också definiera dataflödet för att ange vilka programdata som placeras i genererade dokument. I ER-ramverket genereras utgående dokument i Microsoft Office-format (Excel-arbetsböcker eller Word-dokument) med hjälp av fördefinierade mallar. Mallarna fylls med data som krävs i enlighet med konfigurerat dataflöde när de dokument som krävs skapas. Varje konfigurerat format kan publiceras som en del av en ER-lösning för att generera specifika utgående dokument. Detta representeras av en ER-formatkonfiguration som kan innehålla mallar som du kan använda för att generera olika utgående dokument. Företagsanvändare kan använda det här ramverket för att hantera nödvändiga affärsdokument.

**Hanteringen av affärsdokument** bygger vidare på ER-ramverket och gör det möjligt för affärsanvändare att redigera affärsdokumentmallar genom att använda Microsoft 365-tjänst eller lämpligt Microsoft Office-skrivbordprogram. Ändringar i dokumenten kan inkludera ändring av affärsdokumentdesign och att lägga till platshållare för ytterligare data utan källkodsändringar och nya distributioner. Det krävs ingen kunskap om ER-ramverk för uppdatering av mallar för affärsdokument.

> [!NOTE]
> Tänk på att hanteringen av affärsdokument gör det möjligt att ändra mallar som används för att skapa affärsdokument som t.ex. order, fakturor osv. När en mall har ändrats och en ny version av den har publicerats, används den här versionen för att generera nödvändiga affärsdokument. Det går inte att använda hantering av affärsdokument för att ändra redan genererade affärsdokument.

## <a name="supported-deployments"></a>Distributioner som stöds

För närvarande implementeras funktionen för hantering av affärsdokument endast för molndistributioner. Om den här funktionen är viktig för din lokala distribution kan du meddela oss genom att ge feedback på [Förslag](https://experience.dynamics.com/ideas/)-webbplatsen.

## <a name="supported-microsoft-office-applications"></a>Microsoft Office-program som stöds

Om du vill använda hantering av affärsdokument för att redigera mallar i Excel- eller Word-format med hjälp av Microsoft Office-skrivbordsprogram måste du ha Microsoft Office 2010 eller senare installerat. Detta stöds inte i moln och lokala installationer.

Om du vill använda hantering av affärsdokument för att redigera mallar i Excel- eller Word-format med hjälp av Microsoft 365-appar måste du ha Microsoft 365 Office för webbprenumerationen. Det här stöds i molnbaserad distribution.

## <a name="business-document-availability"></a>Affärsdokuments tillgänglighet

En fullständig lista över alla rapporter planerade för oktober 2019-utgåvan finns i [Konfigurerbar affärsdokumentrapportering i Word och Excel](/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details).

En fullständig lista över alla rapporter planerade för oktober 2020-utgåvan finns i [Konfigurerbar affärsdokumentrapportering – Word-mallar](/dynamics365-release-plan/2020wave1/dynamics365-finance/configurable-business-documents-word-templates).

Fler rapporter blir tillgängliga i framtida versioner. Särskilda meddelanden om ytterligare rapporter kommer att skickas separat. Mer information om hur du granskar listan över tillgängliga rapporter finns i avsnittet [Lista över ER-konfigurationer som har frisläppts i Finance för att stödja konfigurerbara affärsdokument](#list-of-configurations-cbd) nedan.

Om du vill veta mer om den här funktionen fyller du i exemplet i den här artikeln.

## <a name="configure-er-parameters"></a>Konfigurera ER-parametrar

Eftersom hanteringen av affärsdokument skapas ovanpå ER-ramverket måste du konfigurera ER-parametrarna för att kunna börja arbeta med hantering av affärsdokument. Om du vill göra detta måste du ställa in ER-parametrarna enligt beskrivningen i [Konfigurera ER-ramverket (elektronisk rapportering)](electronic-reporting-er-configure-parameters.md). Du måste också lägga till en ny konfigurationsleverantör enligt beskrivningen i [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![ER-arbetsyta.](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>Importera ER-lösningar

Exempel på ER-konfigurationer används i exemplet på denna procedur. Du måste importera till den aktuella instansen av Dynamics 365 Finance, ER-konfigurationer som innehåller de affärsdokumentmallar som kan redigeras med hjälp av hantering av affärsdokument. Hämta följande filer och spara lokalt för att slutföra den här proceduren.

**Exempel på ER-kundfaktureringslösning**

| Fil                                      | Innehåll |
|-------------------------------------------|---------|
| Customer invoicing model.version.2.xml    | [Exempel på konfiguration av ER-datamodell.](https://download.microsoft.com/download/b/f/a/bfa5cb52-e6e2-42bc-a4c0-77014a4c54e6/Customerinvoicingmodel.version.2.xml) |
| Customer FTI report (GER).version.2.3.xml | [Konfiguration för fritextfaktura i ER-format](https://download.microsoft.com/download/3/c/2/3c2e58f2-6e56-43d9-85ea-4c97252a108d/CustomerFTIreportGER.version.2.3.xml) |

**Exempel på lösning för ER-betalningscheckar**

| Fil                                     | Innehåll |
|------------------------------------------|---------|
| Model for cheques.version.10.xml         | [Exempel på konfiguration av ER-datamodell.](https://download.microsoft.com/download/3/7/6/376cb0f6-181a-4895-a432-390ffca64162/Modelforcheques.version.10.xml) |
| Cheques printing format.version.10.9.xml | [Konfiguration för ER-format för betalningscheck](https://download.microsoft.com/download/6/d/6/6d61bfff-3d89-4377-9e34-2e3ee6d6df91/Chequesprintingformat.version.10.9.xml) |

**Exempel på ER-lösning för utländsk handel**

| Fil                             | Innehåll |
|----------------------------------|---------|
| Intrastat model.version.1.xml    | [Exempel på konfiguration av ER-datamodell.](https://download.microsoft.com/download/2/0/0/200d6ed1-eff8-48ec-ab75-175a4acf9714/Intrastatmodel.version.1.xml) |
| Intrastat report.version.1.9.xml | [ER-formatkonfiguration för rapporten för Intrastat-kontroll](https://download.microsoft.com/download/7/a/2/7a2a27c3-a8a5-42a1-9d04-f0a8e1ec1707/Intrastatreport.version.1.9.xml) |

Använd följande procedur för att importera varje fil. Importera konfigurationen för ER-*datamodell* för varje ER-lösning i tabellerna ovan innan du importerar motsvarande ER-*format* konfiguration.

1. Öppna sidan **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. Välj **Växel** högst upp på sidan.
3. Välj **Läs in från XML-fil**.
4. Välj **Bläddra** om du vill läsa in den nödvändiga XML-filen.
5. Välj **OK** för att bekräfta konfigurationens import.

![Sidan för ER-konfigurationer som bekräftar konfigurationsimport.](./media/BDM-Overview-ERSolutions.png)

Du kan också importera de officiellt publicerade ER-formatkonfigurationerna från Microsoft Dynamics Lifecycle Service (LCS). Om du till exempel vill utföra den här proceduren kan du importera den senaste versionen av ER-formatkonfigurationen **Fritextfaktura (Excel)**. De motsvarande konfigurationerna för ER-datamodell och ER-modellmappning kommer att importeras automatiskt.

![Innehållssida för LCS-delade tillgångsbibliotek.](./media/BDM-Overview-SharedAssetLibrary.png)

Mer information om att importera ER-konfigurationer finns i [Hantera livscykeln för konfiguration av elektronisk rapportering](general-electronic-reporting-manage-configuration-lifecycle.md).

## <a name="enable-business-document-management"></a>Aktivera hantering av affärsdokument

Om du vill starta hantering av affärsdokument måste du öppna arbetsytan **Funktionshantering** och aktivera funktionen **Hantering av affärsdokument**.

Använd följande procedur om du vill aktivera funktionen för hantering av affärsdokument för alla juridiska personer.

1. Öppna arbetsytan **Funktionshantering**.
2. På fliken **Ny** väljer du funktionen **Hantering av affärsdokument** i listan.
3. Välj **Aktivera nu** om du vill aktivera den valda funktionen.
4. Uppdatera sidan för att komma åt den nya funktionen.

> [!NOTE]
> Mer information om hur du använder det nya användargränssnittet för hanteringen av affärsdokument finns i: [Nytt användargränssnitt för hanteringen av affärsdokument](er-business-document-management-new-template-ui.md).

![Arbetsytan Funktionshantering.](./media/BDM-Overview-FMEnabling.png)

Mer information om hur du aktiverar nya funktioner finns i [Översikt över funktionshantering](../../fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-parameters"></a>Konfigurera parametrar

Använd informationen i följande avsnitt om du vill ställa in de grundläggande parametrarna för hantering av affärsdokument.

### <a name="prerequisites-for-parameter-setup"></a>Förutsättningar för parameterinställningar

Innan du kan ställa in affärsdokumenthantering måste du ställa in den obligatoriska dokumenttypen i ramverket för dokumenthantering. Den här dokumenttypen används för att ange tillfällig lagring av dokument i Office-format (Excel och Word) som används som mallar för ER-rapporter. Mallen i tillfällig lagring kan redigeras med hjälp av Office-programmen.

För den här dokumenttypen måste följande attributvärden väljas.

| Attributnamn | Attributvärde |
|----------------|-----------------|
| Klass          | Koppla fil     |
| Grupp          | Fil            |
| Plats       | SharePoint      |

Information om hur du ställer in de obligatoriska parametrarna för dokumenthantering och dokumenttyper finns i [Konfigurera dokumenthantering](../../fin-ops/organization-administration/configure-document-management.md).

![Ställ in dokumenttyp för dokumenthantering.](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a><a name="SetupBdmParameters"></a>Ställa in parametrar

Grundläggande inställningar för affärsdokumenthantering kan ställas in på sidan **Parametrar för affärsdokument**. Endast vissa användare har åtkomst till sidan. Dessa innefattar:

- Användare som tilldelats rollen **Systemadministratör**.
- Användare som har tilldelats någon roll som är konfigurerad för att utföra uppdraget **Underhåll parametrar för affärsdokument** (AOT-namn **ERBDMaintainParameters**).

Använd följande procedur om du vill ställa in de grundläggande parametrarna för alla juridiska personer.

1. Logga in som en användare med åtkomst till sidan **Parametrar för affärsdokument**.
2. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Hantering av affärsdokument** \> **Parametrar för affärsdokument**.
3. På sidan **Parametrar för affärsdokument**, på fliken **Bilagor**, i fältet **SharePoint-dokumenttyp**, definierar du den dokumenttyp som ska användas för att tillfälligt spara mallar i Office-format när de redigeras med Office-programmen. 

> [!NOTE]
> Endast dokumenttyper som konfigureras med hjälp en SharePoint-plats är tillgängliga för den här parametern.

![Ställ in parametrar för hantering av affärsdokument.](./media/BDM-Overview-BDMSetting.png)

Den valda dokumenttypen är företagsspecifik och används när användaren arbetar med affärsdokumenthantering i det företag för vilket den valda dokumenttypen konfigurerats. När användaren arbetar med affärsdokumenthantering i ett annat företag används samma dokumenttyp om ingen har konfigurerats för det här företaget. När en dokumenttyp har konfigurerats kommer den att användas istället för den som har valts i fältet **SharePoint-dokumenttyp**.

> [!NOTE]
> Parametern **SharePoint dokument typ** definierar en SharePoint-mapp som tillfällig lagringsplats för mallar som kan redigeras med antingen Microsoft Excel eller Word. Du måste ställa in den här parametern om du tänker använda de här Office-programmen för att redigera mallar. Mer information finns i [Redigera en mall i Office skrivbordsprogrammet](#EditInOfficeDesktopApp). Du kan behålla den här parametern tom om du planerar att ändra mallen genom att endast använda funktionen i Microsoft 365. Mer information finns i [Redigera en mall i Microsoft 365](#EditInOffice365).

## <a name="configure-access-permissions"></a>Konfigurera åtkomstbehörigheter

När åtkomst till behörigheter för affärsdokumenthantering inte har aktiverats, som standard kommer alla användare som har till gång till arbetsytan för affärsdokumenthantering att se alla ER-mallar som är tillgängliga. På arbetsytan för affärsdokumenthantering visas endast de mallar som finns i ER-formatkonfigurationer och som är markerade med en **Affärsdokumenttyp**-tagg.

![ER-konfigurationssida med tagg för affärsdokumenttyp.](./media/BDM-Overview-ERFormatTags.png)

Listan med mallar som är tillgängliga i arbetsytan affärsdokumenthantering kan begränsas genom konfigurering av åtkomstbehörigheter. Detta kan vara viktigt när olika mallar används för att skapa affärsdokument för olika affärsdomäner (funktionsområden) och du vill tillåta specifika användare tillgång till olika mallar för redigering på arbetsytan för affärsdokumenthantering.

Åtkomstbehörigheter till affärsdokumenthantering kan anges i **Konfigurerare för åtkomstbehörigheter**. Endast följande användare har åtkomst till sidan:

- Användare som tilldelats rollen **Systemadministratör**.
- Användare som har tilldelats till någon annan roll som är konfigurerad för att utföra uppdraget **Konfigurera behörigheter för åtkomst till affärsdokumentmallar för redigering** (AOT-namn **ERBDTemplatesSecurity**).

Använd följande procedur om du ställa in behörigheter för åtkomst till hantering av affärsdokument för alla juridiska personer.

1. Logga in som en användare med åtkomst till sidan **Konfigurerare för åtkomstbehörigheter**.
2. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Hantering av affärsdokument** \> **Hantera åtkomstbehörigheter**.

    Titta på det meddelande som informerar dig om att användning av åtkomstbehörigheterna för hantering av affärsdokument för närvarande inte är aktiverade.

    ![Konfigurerare för sidan för åtkomstbehörigheter för hantering av affärsdokument.](./media/BDM-Overview-TemplatesAccess1.png)

    Med den här inställningen kan alla användare som tilldelats en säkerhetsroll som konfigurerats för att utföra uppdraget **Hantera affärsdokumentmallar** (AOT-namn **ERBDManageTemplates**) öppna arbetsytan för affärsdokumenthantering och kan redigera alla mallar som finns.

    Följande bild visar vad som finns på arbetsytan för affärsdokumenthantering för användare som tilldelats rollen **Kundreskontraansvarig**. Med den aktuella inställningen för åtkomstbehörigheter kan användaren redigera mallar för affärsdokument från olika funktionsområden inklusive fakturering, lagstadgad rapportering och betalningar.

    ![Sidan Arbetsyta för hantering av affärsdokument för Kundreskontraansvarig.](./media/BDM-Overview-TemplatesForAlice1.png)

3. På sidan **Konfigurerare för åtkomstbehörigheter**, välj **Inställning för åtkomstbehörighet**.
4. I dialogrutan **Inställningar av åtkomstbehörigheter för att redigera mallar**, aktivera alternativet **Använd konfigurerade åtkomstbehörigheter**.
5. Välj **OK** för att bekräfta att åtkomstbehörigheter för affärsdokumenthantering har aktiverats.

    ![Bekräfta åtkomstbehörigheter för hantering av affärsdokument.](./media/BDM-Overview-TemplatesAccess2.png)

6. Välj **Lägg till** om du vill ange en ny affärsroll för vilken behörigheter för åtkomst till mallar för affärsdokumenthantering måste konfigureras.
7. I dialogrutan **Säkerhetsroller**, välj först rollen **Kundreskontraansvarig** och sedan **OK** för att bekräfta rollvalet.
8. På fliken **Åtkomstbehörigheter per taggar med konfigurationer**, välj **Ny**.
9. I fältet **Taggtyp**, välj **Funktionsområdet** och välj **Fakturera** i fältet **ID**.
10. Välj **Spara** om du vill lagra konfigurerade åtkomstbehörigheter för den valda rollen.

    Den aktuella inställningen betyder att för alla användare som tilldelats rollen **Kundreskontraansvarig** och utför uppdraget **Hantera affärsdokumentmallar** (AOT-namn **ERBDManageTemplates**), kommer konfigurationsmallar för ER-format som har värdet **Faktura** för **Funktionsområde**-taggen att vara tillgängliga för redigering på arbetsytan för affärsdokumenthantering.

11. Växla fönstret **Relaterad information** från den högra sidan av den aktuella sidan. I fönstret **Relaterad information** visas hur de konfigurerade åtkomstbehörigheterna kommer att användas, inklusive vilka ER-konfigurationsmallar som kommer att vara tillgängliga för användare som tilldelats rollen **Kundreskontraansvarig**.

    ![Fönstret Relaterad information på sidan Konfigurerare för åtkomstbehörigheter.](./media/BDM-Overview-TemplatesAccess3.png)

12. På fliken **Åtkomstbehörigheter per konfigurationer**, välj alternativet **Lägg till**.
13. I dialogrutan **Välj konfiguration**, markera ER-formatkonfigurationen **Intrastat-rapport**.
14. Välj **OK** för att bekräfta registreringen av de valda konfigurationerna och välj sedan **Spara** för att lagra de konfigurerade åtkomstbehörigheterna för den valda rollen.

Den aktuella inställningen betyder att för alla användare som tilldelats rollen **Kundreskontraansvarig** och utför uppdraget **Hantera affärsdokumentmallar** (AOT-namn **ERBDManageTemplates**), kommer följande mallar att vara tillgängliga för redigering på arbetsytan för affärsdokumenthantering:

- Mallar som har värdet **Faktura** för taggen **Funktionsområde**.
- Mallar från ER-formatkonfigurationer som anges på fliken **Åtkomstbehörigheter per konfigurationer** (mallar från formatkonfigurationen **Intrastat-rapport** i domänen **Rapportering enligt lag** i det här exemplet).

![Snabbfliken Åtkomstbehörigheter på sidan Konfigurerare för åtkomstbehörigheter.](./media/BDM-Overview-TemplatesAccess4.png)

Följande bild visar vad som finns på arbetsytan för affärsdokumenthantering för en användare som tilldelats rollen **Kundreskontraansvarig**. Med inställningen för åtkomstbehörighet för affärsdokumenthantering kan användaren redigera mallar för affärsdokument från domänen **Fakturera** och ER-formatkonfigurationen **Intrastat-rapport**. Mallar från domänen **Betalningar** är inte tillgängliga för rollen **Kundreskontraansvarig**.

![Redigera affärsdokumentmallar på sidan Arbetsyta för hantering av affärsdokument.](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> Reglerna för **Åtkomstbehörigheter per konfigurationer** lagras med hjälp av det unika ID-numret för en ER-format konfiguration. Detta innebär att dessa regler inte tas bort när en ER-konfiguration som refererar till dem tas bort. När du importerar borttagna konfigurationer tillbaka till den här instansen refererar dessa regler till dem igen. Du behöver inte ställa in reglerna igen när de borttagna konfigurationerna importeras igen.

## <a name="use-business-document-management-to-edit-templates"></a>Använda affärsdokumenthantering för att redigera mallar

Företagsanvändare har åtkomst till affärsdokumentmallar för redigering på arbetsytan för affärsdokumenthantering. Endast följande användare har åtkomst till arbetsytan för affärsdokumenthantering:

- Användare som tilldelats rollen **Systemadministratör**.
- Användare som har tilldelats en roll som är konfigurerad för att utföra uppdraget **Hantera affärsdokumentmallar** (AOT-namn **ERBDManageTemplates**).

Använd följande procedur om du vill redigera mallar för fritextfakturor på arbetsytan affärsdokumenthantering. Innan du slutför den här proceduren måste du ha slutfört alla föregående procedurer i den här artikeln.

1. Logga in som en användare med åtkomst till sidan arbetsyta för hantering av affärsdokument.
2. Öppna arbetsytan för hantering av affärsdokument.

När funktionen **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** är inaktiverad i arbetsytan **funktionshantering** visar huvudrutnätet i arbetsytan **Hantering av affärsdokument** följande mallar:

- Mallar som ägs av din ER-konfigurationsleverantör (dvs. den leverantör som för närvarande är markerad som aktiv i arbetsytan **elektronisk rapportering**). När du har valt en av dessa mallar kan du välja **redigera mall** och starta eller fortsätta att redigera den.
- Mallar som ägs av andra ER-konfigurationsleverantörer. När du har valt en av dessa mallar kan du välja **Nytt dokument** för att skapa en kopia av det som ägs av din ER-konfigurationsleverantör och sedan börja redigera kopian.

![Mallistor på sidan Arbetsyta för hantering av affärsdokument.](./media/BDM-Overview-EditingTemplate1.png)

Fliken **Mall** visar innehållet i den valda mallen. Välj fliken **Detaljer** om du vill visa information om den valda mallen samt information om en ER-formatkonfiguration som den här mallen finns i. Lägg märke till att alla mallar har statusen **Publicerad** och inte innehåller någon information i kolumnen **Ändring**. Detta innebär att dessa mallar inte redigeras just nu.

När funktionen **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** aktiveras i arbetsytan **funktionshantering** visar rutnätet i arbetsytan **Hantering av affärsdokument** visas mallar som ägs av er ER-konfigurationsleverantör (dvs. den leverantör som för närvarande är markerad som aktiv i arbetsytan **elektronisk rapportering**). När du har valt en av dessa mallar kan du välja **redigera mall** och starta eller fortsätta att redigera den.

Om du vill arbeta med mallar som ägs av andra ER-konfigurationsleverantörer väljer du **nytt dokument** för att skapa en kopia av mallen som ägs av din ER-leverantör. Du kan sedan börja redigera kopian. För mer information, se [Nytta användargränssnitt för dokument vid affärsdokumenthantering](er-business-document-management-new-template-ui.md).

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>Initiera redigeringsmallar som ägs av din konfigurationsleverantör

1. På arbetsytan för hantering av affärsdokument väljer du mallen **Checkar utskriftsformat** i listan.
2. Välj fliken **Detaljer**.

![Sidan Arbetsyta för hantering av affärsdokument, fliken Detaljer.](./media/BDM-Overview-EditingTemplate2.png)

Alternativet **Redigera mall** är tillgängligt för den valda mallen. Det här alternativet är alltid tillgängligt för en mall i en ER-formatkonfiguration som ägs av den aktiva ER-konfigurationsleverantören (**Litware, Inc.** i det här exemplet). När du har valt **Redigera mall** kommer den befintliga mallen från utkastversionen av den underliggande ER-formatkonfigurationen att vara tillgänglig för redigering.

### <a name="initiate-editing-templates-owned-by-other-providers"></a>Initiera redigeringsmallar som ägs av andra leverantörer

1. Markera det dokument som du vill använda som mall i arbetsyta för hantering av affärsdokument.

    ![Välj ett dokument på sidan Arbetsyta för hantering av affärsdokument.](./media/BDM-Overview-EditingTemplate3.png)

2. Välj **Nytt dokument** och i fältet **Rubrik** ändra titeln på den redigerbara mallen om det behövs. Texten kommer att användas som namn på den konfiguration för ER-format som skapas automatiskt. Lägg märke till att utkastversionen av den här konfigurationen (**Kopia av FTI-rapport för kund (GER)**) som kommer att innehålla den redigerade mallen automatiskt markeras för att köra det här ER-formatet för den aktuella användaren. På samma gång används den icke ändrade ursprungliga mallen från baskonfigurationen för ER-format för att köra det här ER-formatet för andra användare.
3. I fältet **Namn** ändrar du namnet på den första revisionen av den redigerbara mallen som ska skapas automatiskt.
4. I fältet **Kommentar** ändrar du kommentaren för automatiskt skapade versionen av den redigerbara mallen.
5. Välj **OK** för att bekräfta starten av redigeringsprocessen.

![Bekräfta början på redigeringsprocessen om du vill skapa en ny mall.](./media/BDM-Overview-EditingTemplate4.png)

Om det inte finns någon leverantör kommer ett erbjudande om att skapa en sådan. Om det inte finns någon aktiv leverantör får du möjlighet att välja en för aktivering.

Om du vill skapa en leverantör ändrar du namnet på leverantören i fältet **Namn**, uppdaterar internetadressen för den nya leverantören i fältet **Internetadress** och väljer sedan **OK** för att bekräfta.

   ![Skapa ny leverantör i BDM.](./media/bdm_create_provider.png)

Om du vill aktivera befintlig leverantör väljer du namnet på leverantören i fältet **Konfigurationsleverantör** och väljer sedan **OK** för att ange leverantören som aktiv.

   ![Aktivera leverantör i BDM.](./media/bdm_choose_provider.png)

> [!NOTE]
> Varje BDM-mall refererar till leverantören som författare av konfigurationen. Därför krävs en aktiv leverantör för mallen.


Alternativet **Nytt dokument** är alltid tillgängligt för en mall i en ER-formatkonfiguration som tillhandahålla av en aktuell och en annan leverantör (Microsoft i det här exemplet) som inte har någon ändring. Den redigerade mallen kommer sedan att lagras i en ny konfiguration för ER-format som skapas automatiskt.



### <a name="start-editing-a-template"></a>Börja redigera en mall

1. Välj **Redigera dokument** från den valda mallen.
2. I fältet **Namn** ändrar du namnet på den första revisionen av den redigerbara mallen som ska skapas automatiskt.
3. I fältet **Kommentar** ändrar du anmärkningen för automatiskt skapade versionen av den redigerbara mallen.

    ![Redigera en mall på sidan Arbetsyta för hantering av affärsdokument.](./media/BDM-Overview-EditingTemplate5.png)

4. Välj **OK** för att bekräfta starten av redigeringsprocessen.

Sidan **BDM-mallredigerare** öppnas. Den valda mallen blir tillgänglig för redigering online med hjälp av Microsoft 365.

![Redigeringssida för mall för affärsdokumenthantering.](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-microsoft-365"></a><a name="EditInOffice365"></a>Redigera en mall i Microsoft 365

Du kan inte ändra mall med Microsoft 365. Ändra till exempel teckensnittet för fältfrågan i mallhuvudet från **Vanligt** till **Fetstil** i Office Online. Dessa ändringar sparas automatiskt för den redigerbara mallen som lagras i den primära mallens lagringsutrymme (som standard Azure blob-lagringen). Detta är konfigurerat för ER-ramverket.

![Ändra teckensnitt till fetstil i mallrubriken på redigeringssidan för mall för affärsdokumenthantering.](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a><a name="EditInOfficeDesktopApp"></a>Redigera en mall i Office-skrivbordsprogrammet

> [!NOTE]
> Den här funktionen är endast tillgänglig om parametern **SharePoint dokumenttyp** är korrekt konfigurerad. Mer information finns i [Konfigurera parametrar](#SetupBdmParameters).

1. Välj alternativet **Öppna i skrivbordsprogram** om du vill ändra mallen med hjälp av funktionerna i Office-skrivbordsprogrammet (Excel i det här exemplet). Den redigerbara mallen kopieras från det permanenta lagringsutrymmet till den tillfälliga lagring som har konfigurerats i affärsdokumentparametrarna som en SharePoint-mapp.
2. Bekräfta att du vill öppna mallen från den temporära lagringsplatsen i Office-skrivbordsprogrammet Excel.

    ![Mall som öppnas i skrivbordsprogrammet Excel.](./media/BDM-Overview-EditingLayout3.png)

3. Ändra mallen. Ändra till exempel teckensnittet för fältfrågan i mallhuvudet genom att uppdatera färg från **Svart** till **Blå**.

    ![Ändra teckenfärgen i mallrubriken med hjälp av skrivbordsprogrammet Excel.](./media/BDM-Overview-EditingLayout4.png)

4. Välj **Spara** i Excel-skrivbordsprogrammet för att lagra malländringarna i den tillfälliga lagringen.

    ![Spara ändringarna på sidan för mallen för affärsdokumenthantering med hjälp av skrivbordsprogrammet Excel.](./media/BDM-Overview-EditingLayout5.png)

5. Stäng Excel-skrivbordsprogrammet.
6. Välj **Synkronisera lagrad kopia** om du vill synkronisera den tillfälliga mallagringen till den permanenta mallagringen.

> [!NOTE]
> Kopian av den redigerbara mallen i den tillfälliga fillagringen behålls bara för den aktuella sessionen för redigering av mallar. När du avslutar den här sessionen genom att stänga sidan med **BDM-mallredigeraren** tas den här kopian bort. Om du har justerat mallen i den temporära filen och inte valt **Synkronisera lagrad kopia** visas ett meddelande som frågar om du vill spara ändringarna när du försöker stänga sidan med **BDM-mallredigeraren**. Välj **Ja** om du vill spara ändringarna i mallen på en permanent filplats.

### <a name="validate-a-template"></a>Validera en mall

1. Välj **Sök efter problem** på sidan för **BDM-mallredigeraren** för att validera den ändrade mallen mot den underliggande ER-formatkonfigurationen. Följ rekommendationerna (om det finns några) för att justera mallen efter strukturen på formatet från baskonfigurationen för ER-format.
2. Välj **Visa format** om du vill visa den aktuella strukturen för formatet från baskonfigurationen av ER-format som måste justeras med den redigerbara mallen. 
3. Välj **Dölj format** för att stänga fönstret.

    ![BDM Sidan BDM-mallredigerare.](./media/BDM-Overview-EditingTemplate6.png)

4. Stäng sidan **BDM-mallredigerare**.

Den uppdaterade mallen visas på fliken **Mall**. Observera att statusen för den redigerade mallen nu är **Utkast** och den aktuella revisionen är inte längre tom. Detta innebär att processen för den här mallens redigering har startats.

![Visa den uppdaterade mallen på sidan Arbetsyta för hantering av affärsdokument.](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>Testa den ändrade mallen 

1. I appen, växla till företaget **USMF**.
2. Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.
3. Välj **FTI-00000002**-fakturan och välj sedan **Utskriftshantering**.
4. Välj nivån **Modul – Kundreskontra** \> **Dokument** \> **Fritextfaktura** \> **Ursprungsdokument** för att ange omfånget med fakturor för bearbetning.
5. I fältet **Rapportformat**, välj ER-formatet **Kopia av FTI-rapport för kund (GER)** för den angivna dokumentnivån.

    ![Sidan Inställning för utskriftshantering.](./media/BDM-Overview-TestRun1.png)

6. Tryck på **Esc** för att stänga den aktuella sidan.
7. Välj **Skriv ut** och klicka sedan på **Markerade**.
8. Hämta dokumentet och öppna det med hjälp av skrivbordsprogrammet Excel.

![Sidan Fritextfakturor.](./media/BDM-Overview-TestRun2.png)

Den modifierade mallen används för att generera fritextfakturarapporten för den valda artikeln. Om du vill analysera hur den här rapporten påverkas av de ändringar som du har gjort i mallen kan du köra den här rapporten i en programsession direkt efter att du har ändrat mallen i en annan programsession.

### <a name="create-an-alternative-template-revision"></a>Skapa en alternativ mallversion

1. Öppna sidan **BDM-mallredigerare** och välj mallen **Kopia av FTI-rapport för kund (GER)**.
2. På fliken **Ändringar**, välj **Ny**.
3. Om det behövs ändrar du namnet på den andra revisionen i fältet **Namn** och baserar det på den för tillfället aktiva första versionen.
4. Vid behov, i fältet **Kommentar**, ändrar du anmärkningen för automatiskt skapade versionen av den redigerbara mallen.

    ![Skapa revideringarna av mallen på sidan Arbetsyta för hantering av affärsdokument.](./media/BDM-Overview-AddRevision.png)

    Du har skapat en ny version av din mall som har lagrats i den permanenta mallens lagringsutrymme. Nu kan du fortsätta att redigera mallen för den andra versionen som är markerad som aktiv för tillfället.

5. Välj den första versionen och välj sedan **Ställ in aktiv**. Du kan välja en annan version som aktiv om du när som helst vill återgå till den versionen av mallen.
6. Välj den andra versionen och välj sedan **Ta bort**.
7. Välj **OK** för att bekräfta att du vill ta bort den valda versionen. Du kan ta bort alla icke-aktiva versioner när de inte längre behövs.

### <a name="delete-a-modified-template"></a>Ta bort en ändrad mall

1. På sidan **BDM-mallredigerare**, välj fliken **Mall**.
2. Välj **Ta bort**.
3. Om du väljer **OK** för att bekräfta borttagningen tas ER-formatet **Kopia av FTI-rapport för kund (GER)** bort med den ändrade mallen. Välj **Avbryt** om du vill utforska andra alternativ.

### <a name="revoke-changes-of-template"></a>Återkalla ändringar av mall

När du redigerar mallen från ett ER-format som ägs av den aktuella aktiva leverantören kommer du att erbjudas möjligheten att återkalla ändringar som införts för mallen.

![Avvisa ändringar av mallen på sidan Arbetsyta för hantering av affärsdokument.](./media/BDM-Overview-RevokeChanges.png)

1. På sidan **BDM-mallredigerare**, välj fliken **Mall**.
2. Välj **Ångra**.
3. Om du väljer **OK** för att återkalla ändringarna som har gjorts i mallen, kommer den ändrade mallen att ersättas av den ursprungliga mallen och alla ändringar tas bort. När du återkallar ändringar i mallen kommer du att kunna ta bort mallen. Välj **Avbryt** om du vill utforska andra alternativ.

### <a name="publish-a-modified-template"></a>Publicera en ändrad mall

1. På sidan **BDM-mallredigerare**, på fliken **Mall**, välj **Publicera**.
2. Om du väljer **OK** för att bekräfta publiceringen markeras utkastversionen av det härledda ER-formatet **Kopia av FTI-rapport för kund (GER)** som innehåller den ändrade mallen som slutförd. Den ändrade mallen blir tillgänglig för andra användare. I de slutförda versionerna av det här ER-formatet sparas endast den senaste aktiva versionen av mallen. Övriga versioner tas bort. Välj **Avbryt** om du vill utforska andra alternativ.

## <a name="frequently-asked-questions"></a>Vanliga frågeställningar

### <a name="i-selected-edit-document-but-instead-of-going-to-the-bdm-template-editor-page-in-finance-i-was-sent-to-the-microsoft-365-webpage"></a>Jag valde Redigera dokument, men i stället för att gå till sidan BDM-mallredigeraren i Finance skickades jag till Microsoft 365 webbsidan.

Detta är ett känt problem som omfattar Microsoft 365 omdirigeringen. Detta inträffar när du loggar in på Microsoft 365 första gången. Du löser det här problemet genom att välja **Bakåt** i webbläsaren för att gå tillbaka till föregående sida.

### <a name="i-understand-how-to-edit-a-template-by-using-microsoft-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-and-adjust-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-use-the-office-desktop-application-in-the-same-way"></a>Jag förstår hur man redigerar en mall med hjälp Microsoft 365 i den första programsessionen och hur man använder mallen i den andra programsessionen för att justera mallen för att se hur ändringarna påverkar det genererade affärsdokumentet. Kan jag använda Office-skrivbordsprogrammet på samma sätt?

Ja, det kan du. I den första programsessionen, välj **Öppna i skrivbordsprogram**. Din mall lagras i den temporära fillagringen och öppnas i Office-skrivbordsprogrammet. Utför sedan följande steg för att förhandsgranska malländringarna i det genererade affärsdokumentet:

1. Gör ändringarna i mallen med hjälp av Office-skrivbordsprogrammet.
2. Välj **Spara** i Office-skrivbordsprogrammet.
3. På sidan **BDM-mallredigerare** i den första programsessionen, välj **Synkronisera lagrad kopia**.
4. Kör det här ER-mallformatet i den andra programsessionen.

### <a name="when-i-select-open-in-desktop-app-i-receive-the-following-error-message-value-cannot-be-null-parameter-name-externalid-how-do-i-work-around-this-issue"></a>När jag väljer Öppna i skrivbordsprogrammet visas följande felmeddelande: "Värdet får inte vara null. Parameternamn: externalId." Hur undviker jag detta problem?

Troligen loggade du in på den aktuella instansen av appen i Azure AD-domänen som skiljer sig från Azure AD-domänen som användes för att distribuera den här instansen. Eftersom SharePoint-tjänsten, som används för att lagra mallar som gör dem tillgängliga för redigering med hjälp av Office-skrivbordsprogram, tillhör samma domän har vi ingen behörighet att komma åt SharePoint-tjänsten. Lös problemet genom att logga in på den aktuella instansen med hjälp av autentiseringsuppgifterna för en användare med rätt Azure AD-domän.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)

[ER Skapa en konfiguration för rapportgenerering i OPENXML-format (november 2016)](tasks/er-design-reports-openxml-2016-11.md)

[Utforma ER-konfigurationer för rapportgenerering i Word-format](tasks/er-design-configuration-word-2016-11.md)

[Bädda in bilder och former i dokument som du skapar med ER](electronic-reporting-embed-images-shapes.md)

[Konfigurera elektronisk rapportering (ER) för att hämta data till Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)

## <a name="list-of-er-configurations-that-have-been-released-in-finance-to-support-configurable-business-documents"></a><a name="list-of-configurations-cbd"></a>Lista över ER-konfigurationer som har lanserats i Finance för att stödja konfigurerbara affärsdokument

[Listan](general-electronic-reporting.md#list-of-configurations) över ER-konfigurationer för Finance uppdateras regelbundet. Öppna den [globala databasen](er-download-configurations-global-repo.md) för att granska listan över ER-konfigurationer som för närvarande stöds. Du kan [filtrera](../../../finance/localizations/enhanced-filtering-global-repo.md) den globala databasen för att granska listan med ER-konfigurationer som används för att stödja konfigurerbara affärsdokument.

![Filtrera innehållet i den globala databasen på sidan Konfigurationsdatabas.](./media/bdm-overview-filterglobalrepo.gif)

Följande tabell visar en lista över ER-konfigurationer som stöder konfigurerbara affärsdokument och som har frisläppts i Finance till och med december 2020.

| Konfiguration av datamodell.    | Konfiguration av format                           |
|-----------------------------|-------------------------------------------------|
| Fraktsedel – modell        | Fraktsedel (Excel)                          |
|                             | Fraktsedel (Word)                           |
| Modell för certifiering av ursprung | Certifiering av ursprung (Excel)                   |
|                             | Certifiering av ursprung (Word)                    |
| Fakturamodell               | Kunds debetfaktura och kreditfaktura (Excel)          |
|                             | Kunds debetfaktura och kreditfaktura (Word)           |
|                             | Fritextfaktura (Excel)                       |
|                             | Fritextfaktura (Excel) (BH)                  |
|                             | Fritextfaktura (FR) (Excel)                  |
|                             | Fritextfaktura (LT) (Excel)                  |
|                             | Fritextfaktura (LV) (Excel)                  |
|                             | Fritextfaktura (PL) (Excel)                  |
|                             | Fritextfaktura (CZ) (Excel)                  |
|                             | Fritextfaktura (EE) (Excel)                  |
|                             | Fritextfaktura (HU) (Excel)                  |
|                             | Fritextfaktura (TH) (Excel)                  |
|                             | Fritextfaktura (Word)                        |
|                             | Radartiklar för projektkontrakt (Excel)             |
|                             | Radartiklar för projektkontrakt (CZ) (Excel)        |
|                             | Radartiklar för projektkontrakt (Excel) (BH)        |
|                             | Radartiklar för projektkontrakt (HU) (Excel)        |
|                             | Radartiklar för projektkontrakt (LT) (Excel)        |
|                             | Radartiklar för projektkontrakt (PL) (Excel)        |
|                             | Radartiklar för projektkontrakt (Word)              |
|                             | Frisläppning av kvarhållande av projektkund (Excel)      |
|                             | Frisläppning av kvarhållande av projektkund (CZ) (Excel) |
|                             | Frisläppning av kvarhållande av projektkund (HU) (Excel) |
|                             | Frisläppning av kvarhållande av projektkund (LT) (Excel) |
|                             | Frisläppning av kvarhållande av projektkund (PL) (Excel) |
|                             | Frisläppning av kvarhållande av projektkund (TH) (Excel) |
|                             | Frisläppning av kvarhållande av projektkund (Word)       |
|                             | Projektfaktura (Excel)                         |
|                             | Projektfaktura (Word)                          |
|                             | Projektfaktura (AE) (Excel)                    |
|                             | Projektfaktura (CZ) (Excel)                    |
|                             | Projektfaktura (Excel) (BH)                    |
|                             | Projektfaktura (HU) (Excel)                    |
|                             | Projektfaktura (JP) (Excel)                    |
|                             | Projektfaktura (LT) (Excel)                    |
|                             | Projektfaktura (PL) (Excel)                    |
|                             | Projektfaktura (TH) (Excel)                    |
|                             | Projektfaktura, fullständig (MY) (Excel)               |
|                             | Projektfaktura, enkel (MY) (Excel)             |
|                             | Projekthanteringsfaktura (Excel)                  |
|                             | Projekthanteringsfaktura (CZ) (Excel)             |
|                             | Projekthanteringsfaktura (Excel) (BH)             |
|                             | Projekthanteringsfaktura (HU) (Excel)             |
|                             | Projekthanteringsfaktura (JP) (Excel)             |
|                             | Projekthanteringsfaktura (LT) (Excel)             |
|                             | Projekthanteringsfaktura (PL) (Excel)             |
|                             | Projekthanteringsfaktura (Word)                   |
|                             | Förskottsfaktura för inköp (Excel)                |
|                             | Förskottsfaktura för inköp (Word)                 |
|                             | Förskottsfaktura för försäljning (Excel)                   |
|                             | Förskottsfaktura för försäljning (Word)                    |
|                             | Förskottsfaktura för försäljning (PL) (Excel)              |
|                             | Försäljningsfaktura (Excel)                           |
|                             | Försäljningsfaktura (Excel) (BH)                      |
|                             | Försäljningsfaktura (Excel) (CZ)                      |
|                             | Försäljningsfaktura (Excel) (EE)                      |
|                             | Försäljningsfaktura (Excel) (FR)                      |
|                             | Försäljningsfaktura (Excel) (HU)                      |
|                             | Försäljningsfaktura (Excel) (IN)                      |
|                             | Försäljningsfaktura (Excel) (LT)                      |
|                             | Försäljningsfaktura (Excel) (LV)                      |
|                             | Försäljningsfaktura (Excel) (PL)                      |
|                             | Försäljningsfaktura (Excel) (TH)                      |
|                             | Försäljningsfaktura (Word)                            |
|                             | TMS kommersiell faktura (Excel)                  |
|                             | TMS kommersiell faktura (Word)                   |
|                             | Dokument till leverantörsfaktura (Excel)                 |
|                             | Dokument till leverantörsfaktura (CZ) (Excel)            |
|                             | Dokument till leverantörsfaktura (HU) (Excel)            |
|                             | Dokument till leverantörsfaktura (IN) (Excel)            |
|                             | Dokument till leverantörsfaktura (LT) (Excel)            |
|                             | Dokument till leverantörsfaktura (LV) (Excel)            |
|                             | Dokument till leverantörsfaktura (MY) (Excel)            |
|                             | Dokument till leverantörsfaktura (Word)                  |
| Ordermodell                 | Avtalsbekräftelse (Excel)                  |
|                             | Avtalsbekräftelse (Word)                   |
|                             | Bekräftelser av inköpsavtal (Excel)         |
|                             | Bekräftelser av inköpsavtal (Word)          |
|                             | Inköpsorderrad (Excel)                          |
|                             | Inköpsorderrad (CZ) (Excel)                     |
|                             | Inköpsorderrad, förfrågan (CZ) (Excel)             |
|                             | Inköpsorderrad (HU) (Excel)                     |
|                             | Inköpsorderrad, förfrågan (HU) (Excel)             |
|                             | Inköpsorder (Word)                           |
|                             | Inköpsorder, förfrågan (Excel)                  |
|                             | Inköpsorder, förfrågan (Word)                   |
|                             | Försäljningsorder, förfrågan (Excel)                |
|                             | Försäljningsorder, förfrågan (CZ) (Excel)           |
|                             | Försäljningsorder, förfrågan (HU) (Excel)           |
|                             | Försäljningsorder, förfrågan (Word)                 |
| Packningslistemodell          | Behållarinnehåll (Excel)                      |
|                             | Behållarinnehåll (Word)                       |
|                             | Lastlista (Excel)                               |
|                             | Lastlista (Word)                                |
|                             | Plocklista (Excel)                            |
|                             | Plocklista (CZ) (Excel)                       |
|                             | Plocklista (Word)                             |
|                             | Produktionsplocklista (Excel)                    |
|                             | Produktionsplocklista (Word)                     |
|                             | Leveransplocklista för last (Excel)             |
|                             | Leveransplocklista för last (Word)              |
|                             | Leveransplocklista för leverans (Excel)         |
|                             | Leveransplocklista för leverans (Word)          |
|                             | Leveransplocklista för påfyllnad (Excel)             |
|                             | Leveransplocklista för påfyllnad (Word)              |
| Betalningsmodell               | Betalningsavi för kund (Excel)                 |
|                             | Betalningsavi för kund (Word)                  |
|                             | Betalningsavi för leverantör (Excel)                   |
|                             | Betalningsavi för leverantör (Word)                    |
| Offertmodell             | Projektoffert (Excel)                       |
|                             | Projektoffert (Word)                        |
|                             | Anbudsförfrågan (Excel)                   |
|                             | Anbudsförfrågan (acceptera) (Excel)          |
|                             | Anbudsförfrågan (acceptera) (Word)           |
|                             | Anbudsförfrågan (avvisa) (Excel)          |
|                             | Anbudsförfrågan (avvisa) (Word)           |
|                             | Anbudsförfrågan (retur) (Excel)          |
|                             | Anbudsförfrågan (retur) (Word)           |
|                             | Anbudsförfrågning (Word)                    |
|                             | Försäljningsoffert (Excel)                         |
|                             | Försäljningsoffert (CZ) (Excel)                    |
|                             | Försäljningsoffert (HU) (Excel)                    |
|                             | Försäljningsoffert (Word)                          |
|                             | Bekräftelse av försäljningsoffert (Excel)            |
|                             | Bekräftelse av försäljningsoffert (Word)             |
| Avstämningsmodell        | Kontoutdrag för kund, Ext (Excel)             |
|                             | Kontoutdrag för kund, Ext (CN) (Excel)        |
|                             | Kontoutdrag för kund, Ext (Word)              |
|                             | Kontoutdrag för kund, Frankrike (Excel)          |
| Påminnelsemodell              | Kravbrevsnotering (Excel)                  |
|                             | Kravbrevsnotering (CN) (Excel)             |
|                             | Kravbrevsnotering (Word)                   |
|                             | Kundräntefaktura (Excel)                  |
|                             | Kundräntefaktura (Word)                   |
| Waybill-modell               | Lastanbud (Excel)                             |
|                             | Lastanbud (Word)                              |
|                             | Följesedel för inköpsorder (Excel)             |
|                             | Följesedel för inköpsorder (CZ) (Excel)        |
|                             | Följesedel för inköpsorder (Word)              |
|                             | Rutt (Excel)                                   |
|                             | Rutt (Word)                                    |
|                             | Följesedel för försäljningsorder (Excel)                |
|                             | Följesedel för försäljningsorder (CZ) (Excel)           |
|                             | Följesedel för försäljningsorder (LT) (Excel)           |
|                             | Följesedel för försäljningsorder (PL) (Excel)           |
|                             | Följesedel för försäljningsorder (Word)                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
