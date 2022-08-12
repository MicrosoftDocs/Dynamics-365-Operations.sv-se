---
title: Felsökning av fel på bankutdragsfilen
description: Artikeln förklarar hur du åtgärdar problem orsakade av små skillnader i bankutdragsfilen.
author: angelad116
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: kfend
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44658ea48b9f7dae76c34c5f3d8828c9e8c4ac32
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151773"
---
# <a name="bank-statement-file-import-troubleshooting"></a>Felsökning av fel på bankutdragsfilen

[!include [banner](../includes/banner.md)]

>[!NOTE]
>Den här funktionen kommer att avaktiveras i september 2022 – nya användare bör använda elektronisk rapportering.

Det är viktigt att bankutdragsfilen från banken matchar den layout som Microsoft Dynamics 365 Finance stöder. På grund av de strikta standarder som gäller för bankutdrag kommer de flesta integreringar att fungera korrekt. Ibland kan emellertid utdragsfilen inte importeras, eller också har den felaktiga resultat. Vanligtvis orsakas dessa problem av små skillnader i bankutdragsfilen. Denna artikel förklarar hur du korrigerar dessa skillnader och löser problemen.

## <a name="what-is-the-error"></a>Vad består felet av?

Gå till jobbhistoriken för datahantering och dess utförandedetaljer för att hitta felet när du försöker importera en bankutdragsfil. Felet kan hjälpa dig genom att peka på utdraget, saldot eller utdragsraden. Det ger dig emellertid troligtvis inte tillräckligt med information för att hjälpa dig att identifiera det fält eller element som orsakat problemet.

> [!NOTE]
> Importerade bankutdrag kan endast överlappa varandra under en viss tidpunkt.  Till exempel, om ett uttalande slutar klockan 24:00 den 1 januari 2021, kan början på nästa uttalande vara 24:00 1 januari 2021 24:00:00 AM.

## <a name="what-are-the-differences"></a>Vilka skillnader finns det?
Jämför definitionen av bankfilens layout med Finance importdefinitionen, och notera eventuella skillnader i fält och element. Jämför bankutdragsfilen med relaterad Finance-exempelfil. Skillnader i ISO20022-filerna bör vara lätta att se.

## <a name="time-zone-differences-on-imported-bank-statements"></a>Tidszonsskillnader i importerade bankutdrag
Datum- och tidsvärden i importfilen kan skilja sig åt från datum- och tidsvärden som visas i Ekonomi och drift. Du kan förhindra den här avvikelsen genom att ange en tidszonsskillnad på sidan **konfigurera datakällor**. För mer information om hur du anger en inställning av tidszonen, se [Ställ in importprocess för avancerad bankavstämning](set-up-advanced-bank-reconciliation-import-process.md).

## <a name="transformations"></a>Transformeringar
Normalt måste ändringen utföras i en av de tre transformeringarna. Varje transformering skrivs för en viss standard.

| Resursnamn                                         | Filnamn                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV\_till\_BAI2XML\_xslt            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML\_till\_Reconciliation\_xslt | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT\_till\_MT940XML\_xslt          | MT940TXT-to-MT940XML.xslt          |

## <a name="debugging-transformations"></a>Felsökningtransformeringar
### <a name="adjust-the-bai2-and-mt940-files"></a>Justera filerna BAI2 och MT940

Filerna BAI2 och MT940 är textbaserade filer och kräver en justering om du vill aktivera felsökning för Extensible Stylesheet Language-transformeringar (XSLT). Programmet utför denna justering när en fil importeras.

1.  Skapa en XML-fil och kopiera följande text till den.

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  Kopiera innehållet i bankutdragsfilen och klistra in det i XML-filen så att det ersätter **PASTESTATEMENTFILEHERE**.

### <a name="debug-the-xslt"></a>Felsöka XSLT

Mer information finns i <https://msdn.microsoft.com/library/ms255605.aspx>.

1.  Starta Microsoft Visual Studio.
2.  Skapa en konsolapplikation.
3.  Öppna lämplig XSLT.
4.  Klicka på XLST:n och dess egenskapssida.
5.  Ange inmatningen på platsen för bankutdragsfilen.
6.  Definiera en plats och ett filnamn för utdatan.
7.  Ange erforderliga brytpunkter.
8.  I menyn klickar du på **XML** &gt; **Starta XSLT-felsökning**.

### <a name="format-the-xslt-output"></a>Formatera XSLT-utdata

När transformeringen körs skapas en utdatafil som du kan visa i Visual Studio. Använd Ctrl+A, Ctrl+K och Ctrl+D för att snabbformatera utdatafilen.

### <a name="adjust-the-transformation"></a>Justera transformeringen

Justera transformeringen för att få lämpligt fält eller element i bankutdragsfilen. Mappa sedan detta fält eller element med lämpligt Finance-element.

### <a name="debitcredit-indicator"></a>Debet-/kreditindikator

Ibland kan debet importeras som kredit, och kredit kan importeras som debet. För att lösa detta problem måste du ändra lämplig XSLT. Om bankutdrag kommer från flera banker, se då till att alla använder samma debet-/kreditmetod, eller skapa separata transformeringar.

-   BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator-mall
-   ISO20022XML-to-Reconcilation.xslt GetCreditDebit-mall
-   MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator-mall

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exempel på bankutdragsformat och tekniska layouter
Följande tabell anger exempel på tekniska layoutdefinitioner för importfiler för avancerade bankavstämningar, samt tre relaterade bankutdragsexempelfiler. Du kan hämta till exempelfiler och tekniska layouter här: [Exempel på importfiler](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Teknisk layoutdefinition                             | Bankutdragsexempelfil          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]

