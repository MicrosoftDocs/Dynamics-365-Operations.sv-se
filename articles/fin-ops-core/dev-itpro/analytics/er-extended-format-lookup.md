---
title: Utökad formatssökning för elektroniskt rapportering (ER)
description: I det här avsnittet beskrivs hur en ER-formatreferens kan ställas in i ER-formatsökning när det format som krävs lagras i den globala databasen.
author: NickSelin
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 395282eb267e7e356fca6087f99c6f193741ac9d
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605167"
---
# <a name="allow-users-to-set-up-an-er-format-reference-inquiring-a-format-from-the-global-repository"></a>Tillåt användare att ställa in en ER-formatreferens som frågar ett format från den globala databasen

[!include [banner](../includes/banner.md)]

Du kan använda [ramverket för Elektronisk rapportering](general-electronic-reporting.md) (ER) för att konfigurera [format](general-electronic-reporting.md#FormatComponentOutbound) för utgående dokument i enlighet med de lagliga kraven i olika länder/regioner. Du kan också använda ER-ramverket för att konfigurerra [format](general-electronic-reporting.md#FormatComponentInbound) för att analysera inkommande dokument och använda informationen från dessa dokument för att lägga till eller uppdatera applikationsdata. Varje format kan användas i din Dynamics 365 Finance-instans för att hantera inkommande eller utgående affärsdokument som en del av en viss affärsprocess.

Vanligtvis måste du ange vad ER-format som ska användas i en viss affärsprocess. Det gör du genom att välja ett enskilt ER-format i ett uppslagsfält som är konfigurerat som en del av affärsprocessens specifika parametrar. Dessa uppslagsfält implementeras vanligtvis med hjälp av lämplig API för ER-ramverk. Mer information finns i [ER-ramverkets API-kod för att visa en formatmappningssökning](er-apis-app73.md#code-to-display-a-format-mapping-lookup).

När du till exempel konfigurerar [parametrar för utländsk handel](../../../finance/localizations/emea-intrastat.md#set-up-foreign-trade-parameters) måste du ställa in referenserna för enskilda ER-format som ska användas för att generera Intrastat-deklarationen och Intrastat-deklarationen för kontroll. Skärmdumparna nedan visar hur uppslagsfältet för ER-format ser ut på sidan **Utländska handelsparametrar**.

Om den aktuella Finance-instansen inte innehåller några affärsprocessrelaterade ER-format för Intrastat, är det här uppslagsfältet tomt.

[![Parametersida för utländsk handel, tomt fält för mappning av rapportformat.](./media/ER-ExtLookup-Lookup1.gif)](./media/ER-ExtLookup-Lookup1.gif)

Om den aktuella Finance-instansen inte innehåller några affärsprocessrelaterade ER-format för Intrastat, erbjuder det här uppslagsfältet ER-formaten.

[![Parametersida för utländsk handel, tomt fält för mappning av rapportformat med alternativ.](./media/ER-ExtLookup-Lookup2.png)](./media/ER-ExtLookup-Lookup2.png)

Det här uppslaget erbjuder bara de ER-format som redan har importerats till den aktuella Finance-instansen. Om du vill [importera](./tasks/er-import-configuration-lifecycle-services.md) ER-lösningar till den aktuella Finance-instansen måste du ha behörighet att köra rätt funktion i ER-ramverket [livscykel](general-electronic-reporting-manage-configuration-lifecycle.md) av ER-lösningar som innehåller ER-format.

Från Finance versionen 10.0.9 (april 2020 version) har användargränssnittet i uppslaget för ER-format implementerats med hjälp av ER-ramverkets API utökats. Du kan fortfarande välja de befintliga ER-formaten, som på snabbfliken **Välj formatkonfiguration**. Dessutom erbjuder det utökade uppslaget det nya alternativet att söka i den globala databasen (GR) efter specifika ER-format. Alla ER-format i GR erbjuds på snabbfliken **importera från den globala databasen**.

[![Sidan Utländska handelsparametrar, snabbflik för import från den globala databasen.](./media/ER-ExtLookup-Lookup3.png)](./media/ER-ExtLookup-Lookup3.png)

På samma sätt som snabbfliken **Välj formatkonfiguration** visar snabbfliken **Importera från global databas** visar endast de ER-format som är tillämpliga på affärsprocessen för vilken ett ER-format är valt i detta sökfält. I det här exemplet genereras Intrastat-deklaration. ER-formatet kan användas för det företag som användaren för närvarande är inloggad på, beroende på företagets landssammanhang.

När du väljer ett ER-format på snabbfliken **importera från den globala databasen** importeras det valda ER-formatet [konfiguration](general-electronic-reporting.md#Configuration) importeras från GR till den aktuella Finance-instansen.

[![Parametersida för utländsk handel, Bearbetning av verksamhetssedel.](./media/ER-ExtLookup-FormatImport.png)](./media/ER-ExtLookup-FormatImport.png)

Om importen sedan har slutförts lagras referensen till det importerade ER-formatet i sökfältet. När du öppnar GR för första gången måste du följa länken som anges för att registrera dig för [Regulatory Configuration Service](https://aka.ms/rcs) (RCS) som används för att hantera åtkomsten till GR.

[![Parametersida för utländsk handel, Länk för registrering för RCS.](./media/ER-ExtLookup-RepoSignUp.png)](./media/ER-ExtLookup-RepoSignUp.png)

Som standard innehåller snabbfliken **importera från global databas** listan med ER-format från den tillfälliga lagring som skapas automatiskt, baserat på innehållet i GR för prestandaförbättringar. Detta inträffar när snabbfliken **importera från global databas** öppnas första gången, vilket kan ta flera sekunder.

Om du inte ser det nödvändiga ER-formatet på **Importera från global databas** men du är säker på att detta ER-format lagras i GR, väljer, du alternativet **Synkronisera**. Detta alternativ uppdaterar den tillfälliga lagringen och synkroniserar den med det aktuella innehållet i GR.

## <a name="feature-activation"></a>Funktionsaktivering

Tillgängligheten för den här funktionen styrs av den **utökade sökningen efter ER-format-konfigurationer som gör det möjligt att fråga den globala databasen** i **funktionshanteringen**. Den här funktionen aktiveras som standard.

[![Sidan Funktionshantering.](./media/ER-ExtLookup-FeatureMngt.png)](./media/ER-ExtLookup-FeatureMngt.png)

## <a name="security-considerations"></a>Säkerhetsaspekter

Behörigheten **Underhåll konfigurationsdatabaser** (**ERMaintainSolutionRepositories**) kontrollerar åtkomst till GR för en användare som öppnar ER-formatsökning med aktiverade snabbfliken **Importera från global databas**. Om du vill att användarna ska kunna komma åt innehållet i ER-formatsökningen måste du ändra säkerhetsinställningarna genom att bevilja privilegium **ERMaintainSolutionRepositories** till användarna direkt eller använda redan tilldelade roller och uppgifter.

Följande skärmbild visar hur det här privilegiet kan beviljas användare som tilldelats rollen **revisor**. Med den här rollen tillåts användare konfigurera utländska handelsparametrar och ställa in referenser till ER-format i fälten **Filformatmappning** och **Rapportformatmappning** på sidan **Utländska handelsparametrar**.

[![Sidan Säkerhetskonfiguration.](./media/ER-ExtLookup-SecuritySetting.png)](./media/ER-ExtLookup-SecuritySetting.png)

## <a name="limitations"></a>Begränsningar

Åtkomsten till GR i ER-formatsökningen stöds för närvarande bara för val av ER-format som används för att generera utgående dokument.

## <a name="frequently-asked-questions"></a>Vanliga frågeställningar

### <a name="why-cant-i-access-the-global-repository-from-the-er-format-lookup"></a>Varför kan jag inte komma åt den globala databasen från sökning efter ER-format?

Om du har aktiverat funktionen **Utökad sökning av ER-formatkonfigurationer som gör det möjligt att fråga globala databasen** på sidan **funktionshanteringen** men användare kan inte se ER-format på snabbfliken **importera från global databas** och alternativet **Synkronisera** är synligt men inaktiverat, se till att privilegiet **Underhåll konfigurationsdatabaser** (**ERMaintainSolutionRepositories**) har beviljats användaren. Kontakta systemadministratören om du vill ha den här behörigheten.

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Ramverks-API för elektroniskt rapportering (ER)](er-apis-app73.md)
- [Hantera livscykeln för konfiguration av elektronisk rapportering (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
