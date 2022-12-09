---
title: Gränssnitt för Report Designer
description: Den här artikeln innehåller en beskrivning av hur du navigerar på Report Designer och hur du använder de olika alternativen för att uppfylla dina krav.
author: aprilolson
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 59041
ms.assetid: 054de5b0-8618-4195-be12-f031b4bb4d74
ms.search.form: FinancialReports
ms.openlocfilehash: 25d913e6f5d4c95dceda1291a2c33abe37348574
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802753"
---
# <a name="report-designer-interface"></a>Gränssnitt för Report Designer

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller en beskrivning av hur du navigerar på Report Designer och hur du använder de olika alternativen för att uppfylla dina krav.

## <a name="report-designer-menu-commands"></a>Menykommandon för Report Designer

I tabellen nedan beskrivs menykommandona och alternativen som du kan använda när du utformar ekonomiska rapporter. Vissa menykommandon och alternativ är bara tillgängliga i vissa förhållanden. Exempelvis är kommandona för att främja och att sänka rapportenheter endast tillgängliga om du ändrar en rapportträddefinition.

### <a name="file-menu"></a>Menyn Arkiv

Menyn **ArkivFil** är tillgänglig för alla användare och inkluderar följande kommandon.

| Kommando                           | Beskrivning |
|-----------------------------------|-------------|
| Nytt                               | Skapa en ny rapportdefinition, raddefinition, kolumndefinition, rapportträddefinition, definition för rapportgrupp eller mapp. Det finns fler alternativ beroende på din användarroll. |
| Öppen                              | Öppna en befintlig raddefinition, kolumndefinition, rapportträddefinition eller rapportdefinition. |
| Stäng                             | Stäng det aktuella byggblock. |
| Stäng alla                         | Stäng alla byggblock. |
| Spara                              | Spara nuvarande raddefinition, kolumndefinition, rapportträddefinition eller rapportdefinition. |
| Spara som                           | Spara nuvarande raddefinition, kolumndefinition, rapportträddefinition eller rapportdefinition med ett nytt namn. |
| Egenskaper                        | Öppna dialogrutan **Egenskaper** där du kan ändra namn och beskrivning av en rapport. |
| Skapa                          | Skapa aktuell rapport. Detta kommando är tillgängligt från en rapportdefinition. |
| Visa rapport                       | Öppna den senaste versionen av den skapade rapporten. Detta kommando är tillgängligt från en rapportdefinition, om du har skapat minst en rapport. |
| Senaste rapportdefinitionerna         | Visa en lista med de senast skapade eller ändrade rapporterna. Du kan sedan välja en rapport i listan. |
| Senaste raddefinitionerna            | Visa en lista med de senast skapade eller ändrade raddefinitionerna. Du kan sedan välja en raddefinition i listan. |
| Senaste kolumndefinitionerna         | Visa en lista med de senast skapade eller ändrade kolumndefinitionerna. Du kan sedan välja en kolumndefinition i listan. |
| Tidigare rapportträdsdefinitioner  | Visa en lista med de senast skapade eller ändrade rapportträddefinitionerna. Du kan sedan välja en rapportträddefinition i listan. |
| Avsluta                              | Avsluta Report Designer. |

### <a name="edit-menu"></a>Redigera meny

Menyn **Redigera** är tillgänglig för användare som har rollerna **Designer** eller **Administratör**. Den här menyn innehåller följande kommandon.

| Kommando                                | Beskrivning |
|----------------------------------------|-------------|
| Ångra                                   | Ångra den senaste åtgärden. |
| Gör om                                   | Återför den senaste åtgärden för att ångra. |
| Klipp ut                                    | Ta bort den valda texten och kopiera den till Urklipp |
| Kopiera                                   | Kopiera den valda texten och kopiera den till Urklipp |
| Klistra in                                  | Infoga de senaste urklippta eller kopierade texten från Urklipp. |
| Ta bort                                  | Ta bort innehållet i den valda byggblockscellen. |
| Sök                                   | Öppna dialogrutan **Sök och Ersätt** där du kan söka text i vyfönstret. |
| Ersätta                                | Öppna dialogrutan **Sök och Ersätt** där du kan söka och ersätta text i vyfönstret. |
| Infoga rader från dimensioner            | Öppna dialogrutan **Infoga rader från dimensioner** där du kan välja de dimensionsvärden som ska inkluderas i raddefinitionen. Detta kommando är tillgängligt från en raddefinition. |
| Numrera om rader                          | Numrera om alla numeriska radkoder. Detta kommando är tillgängligt från en raddefinition. |
| Radlänkar                              | Öppna dialogrutan **Radlänkar** där du kan ange källorna för datalänkar i raddefinitioner och rapportträddefinitioner. Detta kommando är tillgängligt från en raddefinition. |
| Avrundningsjustering                    | Öppna dialogrutan **Avrundningsjusteringar** där du kan ange parametrar för avrundning. Detta kommando är tillgängligt från en raddefinition. |
| Hantera dimensionsgrupper                  | Öppna dialogrutan **Dimensionsuppsättningar** där du kan skapa och ändra dimensionsuppsättningar. Detta kommando är tillgängligt från en raddefinition eller en rapportträddefinition. |
| Infoga rad                             | Infoga en tom rad i raddefinitionen eller tom rubrikrad till kolumndefinitionen. Detta kommando är tillgängligt från en raddefinition eller en kolumndefinition. |
| Ta bort rad                             | Ta bort den markerade raden från den valda raddefinitionen eller rubrikraden från kolumndefinitionen. Detta kommando är tillgängligt från en raddefinition eller en kolumndefinition. |
| Infoga kolumn                          | Infoga en tom kolumn till kolumndefinitionen. Detta kommando är tillgängligt från en kolumndefinition. |
| Ta bort kolumn                          | Ta bort den valda kolumnen från kolumndefinitionen. Detta kommando är tillgängligt från en kolumndefinition. |
| Infoga rapportenheter från dimensioner | Öppna dialogrutan **Infoga Rapportenheter från Dimensioner** där du kan välja de dimensionsvärden som ska inkluderas i rapportträddefinitionen. Detta kommando är tillgängligt från en rapportträddefinition. |
| Importera dimensionsgrupphierarki         | Öppna dialogrutan **Hierarki för dimensionsuppsättning** där du kan importera en hierarki för dimensionsuppsättning från de ekonomiska data. Detta kommando är tillgängligt från en raddefinition för ett ..\\financial-dimensions\\dimension-baserat system. |
| Infoga rapportenhet                  | Infoga en tom rad i rapportträddefinitionen. Detta kommando är tillgängligt från en rapportträddefinition. |
| Ta bort rapportenhet                  | Ta bort den valda rapportenhetraden från rapportträddefinitionen. Det här kommandot är tillgängligt i rapportträdsdefinitioner. |

### <a name="view-menu"></a>Visa-menyn

Menyn **Visa** är tillgänglig för alla användare och inkluderar följande kommandon.

| Kommando         | Beskrivning                                                            |
|-----------------|------------------------------------------------------------------------|
| Navigeringsfönstret | Visa eller dölja navigeringsfönstret.                                      |
| Verktygsfält        | Välj de verktygsfält som är synliga.                                  |
| Statusfält      | Visa eller dölj statusinformationen i fönstret **Report Designer**. |
| Välkomstsida    | Öppna **Välkomstsidan**.                                             |

### <a name="format-menu"></a>Formatera menyn

Menyn **Format** är tillgänglig för användare som har rollerna **Designer** eller **Administratör**. Den här menyn innehåller följande kommandon.

| Kommando               | Beskrivning |
|-----------------------|-------------|
| Format och formatering | Öppna dialogrutan **Utföranden och formatering** där du kan skapa och ändra utförandet av text i raddefinitioner och kolumndefinitioner. Detta kommando är tillgängligt från en raddefinition eller en kolumndefinition. |
| Kolumnbredd          | Öppna dialogrutan **Kolumnbredden** där du kan ställa in bredden på den valda kolumnen. Detta kommando är tillgängligt från en raddefinition, en kolumndefinition eller en rapportträddefinition. |
| Dölj                  | Dölj den valda kolumnen. Detta kommando är tillgängligt från en raddefinition, en kolumndefinition eller en rapportträddefinition. |
| Visa                | Visa de dolda kolumnerna mellan de markerade kolumnerna. Detta kommando är tillgängligt från en raddefinition, en kolumndefinition eller en rapportträddefinition. |

### <a name="company-menu"></a>Företagsmeny

Menyn **Företag** är tillgänglig för användare som har rollerna **Designer** eller **Administratör**. Den här menyn innehåller följande kommandon.

| Kommando               | Beskrivning                                                                                                            |
|-----------------------|------------------------------------------------------------------------------------------------------------------------|
| Företag             | Öppna dialogrutan **Företag** där du kan skapa och ändra företag.                                          |
| Byggblocksgrupper | Öppna dialogrutan **Grupper för byggblock** där du kan skapa, ändra, importera och exportera grupper för byggblock. |

### <a name="go-menu"></a>Gå till menyn

**Kör**-menyn är tillgänglig för alla användare och innehåller följande kommandon.

> [!NOTE]
> Dessa kommandon har ingen synlig effekt om inte navigeringsfönstret visas.

| Kommandon                   | Beskrivning                                                                        |
|----------------------------|------------------------------------------------------------------------------------|
| Rapportdefinitioner         | Visa rapportdefinitioner i navigeringsfönstret.                                    |
| Raddefinitioner            | Visa raddefinitioner i navigeringsfönstret.                                       |
| Kolumndefinitioner         | Visa kolumndefinitioner i navigeringsfönstret.                                    |
| Rapportträddefinitioner | Visa rapportträddefinitioner i navigeringsfönstret.                            |
| Säkerhet                   | Visa säkerhetsinformation för användare, grupper och företag i navigeringsfönstret. |

### <a name="tools-menu"></a>Menyn Verktyg

Menyn **Verktyg** är tillgänglig för alla användare, men en del kommandon har begränsat tillgänglighet. Den här menyn innehåller följande kommandon.

| Kommando                       | Beskrivning |
|-------------------------------|-------------|
| Skydda                       | Tillämpa ett lösenord till det aktuella byggblocket. Detta kommando är tillgängligt för användare som har rollerna **Designer** eller **Administratör**. |
| Rapportköstatus           | Öppna dialogrutan **Rapportköstatus** där du kan se alla de senaste skapade rapporterna och detaljerna för varje rapport. |
| Information om källsystem     | Visar inställningarna för dina Microsoft Dynamics ERP-system. Detta kommando är tillgängligt för användare som har rollerna **Designer** eller **Administratör**. |
| Utcheckade objekt             | Visa de raddefinitioner, kolumndefinitioner, rapportträddefinitioner och rapportdefinitioner som för närvarande är öppna. Detta kommando är tillgängligt för användare som har rollerna **Designer** eller **Administratör**. |
| Uppdatera cachelagrade ekonomiska data | Uppdatera data i den ekonomiska dimensionkolumnen. |
| Alternativ                       | Öppna dialogrutan **Alternativ** där du kan ändra användarinställningar för Report Designer. |

### <a name="window-menu"></a>Menyn Fönster

Menyn **Fönster** är tillgänglig för alla användare och inkluderar följande kommandon.

| Kommando              | Beskrivning |
|----------------------|-------------|
| Lägga sida vid sida horisontellt    | Visa alla öppna fönster bredvid varandra. |
| Lägga sida vid sida vertikalt      | Visa alla öppna fönster, ovanpå ett annat. |
| Kaskad              | Skikta alla öppna fönster, så att namnlisten för varje fönstret visas. |
| Frysa horisontellt    | Frys den valda raden så att denna rad fortsätter visas i fönstret medan du bläddrar. Detta kommando är tillgängligt för användare som har rollerna **Designer** eller **Administratör**. |
| Frysa vertikalt      | Frys den valda kolumnen så att denna kolumn fortsätter visas i fönstret medan du bläddrar. Detta kommando är tillgängligt för användare som har rollerna **Designer** eller **Administratör**. |
| Lista över öppna fönster | Visa en lista över fönster som är öppna. Välj ett fönster som du vill föra till framsidan. |

### <a name="help-menu"></a>Hjälp-menyn

Menyn **Hjälp** är tillgänglig för alla användare och inkluderar följande kommandon.

| Kommando | Beskrivning                                                              |
|---------|--------------------------------------------------------------------------|
| Hjälp    | Öppna hjälpavsnittsida för ekonomisk rapportering. |
|         |                                                                          |

## <a name="report-designer-toolbar-buttons"></a>Verktygsfältsknappar för Report Designer
Följande tabeller beskriver de verktygsfältsknappar som du kan använda när du utformar rapporter. Vissa verktygsfältsknappar är bara tillgängliga i vissa förhållanden. Exempelvis är knapparna för att främja och att sänka rapportenheter endast tillgängliga om du ändrar en rapportträddefinition.

### <a name="standard-toolbar"></a>Standardverktygsfält

Standardverktygsfältet ger snabb åtkomst till fil- och redigeringskommandon. Detta verktygsfält innehåller följande knappar.

| Knapp                                                                                       | beskrivning |
|----------------------------------------------------------------------------------------------|-------------|
| [![Knappen Ny.](./media/rowc130389.png)](./media/rowc130389.png)                              | Skapa en ny (tom) rapportdefinition, raddefinition, kolumndefinition eller rapportträddefinition. |
| [![Knappen Öppna.](./media/openfolderc130389.png)](./media/openfolderc130389.png)               | Öppna en befintlig raddefinition, kolumndefinition, rapportträddefinition eller rapportdefinition. |
| [![Knappen Spara.](./media/savec130389.png)](./media/savec130389.png)                           | Spara nuvarande raddefinition, kolumndefinition, rapportträddefinition eller rapportdefinition. |
| [![Knappen Kopiera.](./media/copyc130389.png)](./media/copyc130389.png)                           | Kopiera den valda texten och kopiera den till Urklipp |
| [![Knappen Klipp ut.](./media/cutc130389.png)](./media/cutc130389.png)                              | Ta bort den valda texten och kopiera den till Urklipp |
| [![Knappen Klistra in.](./media/pastec130389.png)](./media/pastec130389.png)                        | Infoga text från Urklipp. |
| [![Knappen Ångra.](./media/undoc130389.png)](./media/undoc130389.png)                           | Ångra den senaste åtgärden. |
| [![Knappen Gör om.](./media/redoc130389.png)](./media/redoc130389.png)                           | Återför den senaste åtgärden för att ångra. |
| [![Knappen Sök.](./media/findc130389.png)](./media/findc130389.png)                           | Öppna dialogrutan **Sök och Ersätt** där du kan söka och ersätta text i det aktiva fönstret. |
| [![Knappen Infoga rad.](./media/insertrowc130389.png)](./media/insertrowc130389.png)           | Infoga en tom rad i raddefinitionen eller tom rubrikrad till kolumndefinitionen. Denna knapp är tillgänglig från en raddefinition eller en kolumndefinition. |
| [![Knappen Infoga kolumn.](./media/insertcolumnc130389.png)](./media/insertcolumnc130389.png)  | Infoga en tom kolumn till kolumndefinitionen. Denna knapp är tillgänglig från en kolumndefinition. |
| [![Knappen Lås.](./media/lockc130389.png)](./media/lockc130389.png)                           | Tillämpa ett lösenord till det aktuella byggblocket. Denna knapp är tillgänglig för användare som har rollerna **Designer** eller **Administratör**. |
| [![Knappen Radlänk.](./media/rowlinkc130389.png)](./media/rowlinkc130389.png)                 | Öppna dialogrutan **Radlänkar** där du kan ange källorna för datalänkar i raddefinitioner och rapportträddefinitioner. Denna knapp är tillgänglig från en raddefinition. |
| [![Knappen Flytta upp.](./media/promotec130389.png)](./media/promotec130389.png)                  | Främja en enhet av rapportträddefinitionen. När du väljer en underordnad enhet och sedan klickar på knappen **Främja**, flyttas den underordnade enhet till samma nivå som dess överordnade enhet. |
| [![Knappen Flytta ned.](./media/demotec130389.png)](./media/demotec130389.png)                     | Sänk en enhet av rapportträddefinitionen. När du väljer en enhet och sedan klickar på **Sänk**, blir enheten underordnad den enhet som den kommer ifrån. |
| [![Knappen Visa.](./media/expandtreebuttonc130389.png)](./media/expandtreebuttonc130389.png) | Visar alla enheter av rapportträddefinitionen på nivån för den valda enheten. |
| [![Knappen Dölj.](./media/collapsec130389.png)](./media/collapsec130389.png)               | Döljer rapportträdet. |
| [![Knappen Hjälp.](./media/helpc130389.png)](./media/helpc130389.png)                           | Öppna Hjälp. |

### <a name="formatting-toolbar"></a>Formateringverktygsfält

Formateringverktygsfältet innehåller enkel åtkomst till utförandekommandon. Detta verktygsfält innehåller följande knappar.

| Knapp                                                                                                       | beskrivning                                           |
|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| [![Knappen Teckenstil.](./media/formattingc130389.png)](./media/formattingc130389.png)                         | Tillämpa den valda teckenstilen den till den aktuella texten.   |
| [![Knappen Teckensnitt.](./media/fonttype.png)](./media/fonttype.png)                                                 | Ställ in den aktuella texten med den valda teckenstilen.           |
| [![Knappen Teckenstorlek.](./media/fontsize.png)](./media/fontsize.png)                                            | Ställ in den aktuella texten med den valda teckenstorleken (i punkter). |
| [![Knappen Fetstil.](./media/boldc130389.png)](./media/boldc130389.png)                                           | Gör den aktuella texten fet.                          |
| [![Knappen Kursiv.](./media/italicsc130389.png)](./media/italicsc130389.png)                                   | Gör den aktuella texten kursiv.                        |
| [![Knappen Understrykning.](./media/underlinec130389.png)](./media/underlinec130389.png)                            | Stryker under den aktuella texten.                          |
| [![Knappen Minska indrag.](./media/outdentlsc130389.png)](./media/outdentlsc130389.png)                      | Minskar den aktuella textens indrag.             |
| [![Knappen Öka indrag.](./media/indentlsc130389.png)](./media/indentlsc130389.png)                        | Ökar den aktuella textens indrag.             |
| [![Knappen Bakgrundsfärg.](./media/fillbackgroundcolorc130389.png)](./media/fillbackgroundcolorc130389.png) | Ändra bakgrundsfärgen på den aktuella cellen.     |
| [![Knappen Teckenfärg.](./media/fontcolorc130389.png)](./media/fontcolorc130389.png)                           | Ändra den aktuella textens teckenfärg.                |

### <a name="report-designer-toolbar"></a>Verktygsfält för Report Designer

Verktygsfältet för rapportdesignern ger snabb åtkomst till kommandon navigering i rapportdesignern. Detta verktygsfält innehåller följande knappar.

| Knapp                                                                                              | beskrivning |
|-----------------------------------------------------------------------------------------------------|-------------|
| [![Knappen Rapportdefinition.](./media/reportc130389.png)](./media/reportc130389.png)            | Visa rapportdefinitionen som anges på menyn **Fönster**. |
| [![Knappen Raddefinition.](./media/rowc130389.png)](./media/rowc130389.png)             | Visa den raddefinition som har tilldelats den aktiva rapportdefinitionen. |
| [![Knappen Kolumndefinition.](./media/columnc130389.png)](./media/columnc130389.png)  | Visa den kolumndefinition som har tilldelats den aktiva rapportdefinitionen. |
| [![Knappen Rapportträddefinition.](./media/treec130389.png)](./media/treec130389.png)             | Visa den rapportträddefinition som har tilldelats den aktiva rapportdefinitionen. |
| [![Knappen Rapportvisning.](./media/reportviewerc130389.png)](./media/reportviewerc130389.png)         | Starta Report Viewer och visa den senaste versionen av den skapade rapporten. Denna knapp är tillgänglig från en rapportdefinition, om du har skapat minst en rapport. |
| [![Knappen Skapa rapport.](./media/generate-to-ddvc130389.png)](./media/generate-to-ddvc130389.png) | Skapa en rapport från den aktiva rapportdefinitionen. Den här knappen är tillgänglig från en rapportdefinition. |

## <a name="additional-resources"></a>Ytterligare resurser

[Ekonomisk rapportering](financial-reporting-intro.md)

[Generera ekonomiska rapporter](generate-financial-report.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
