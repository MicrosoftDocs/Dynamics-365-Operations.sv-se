---
title: "Felsökning av fel på bankutdragsfilen"
description: "Det är viktigt att bankutdragsfilen från banken matchar den layout som Microsoft Dynamics 365 for Finance and Operations stöder. På grund av de strikta standarder som gäller för bankutdrag kommer de flesta integreringar att fungera korrekt. Ibland kan emellertid utdragsfilen inte importeras, eller också har den felaktiga resultat. Vanligtvis orsakas dessa problem av små skillnader i bankutdragsfilen. Denna artikel förklarar hur du korrigerar dessa skillnader och löser problemen."
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c408f30c783d58766ab93b13c589079c3ef375de
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="bank-statement-file-import-troubleshooting"></a>Felsökning av fel på bankutdragsfilen

[!include [banner](../includes/banner.md)]

Det är viktigt att bankutdragsfilen från banken matchar den layout som Microsoft Dynamics 365 for Finance and Operations stöder. På grund av de strikta standarder som gäller för bankutdrag kommer de flesta integreringar att fungera korrekt. Ibland kan emellertid utdragsfilen inte importeras, eller också har den felaktiga resultat. Vanligtvis orsakas dessa problem av små skillnader i bankutdragsfilen. Denna artikel förklarar hur du korrigerar dessa skillnader och löser problemen.

<a name="what-is-the-error"></a>Vad består felet av?
------------------

Gå till jobbhistoriken för datahantering och dess utförandedetaljer för att hitta felet när du försöker importera en bankutdragsfil. Felet kan hjälpa dig genom att peka på utdraget, saldot eller utdragsraden. Det ger dig emellertid troligtvis inte tillräckligt med information för att hjälpa dig att identifiera det fält eller element som orsakat problemet.

## <a name="what-are-the-differences"></a>Vilka skillnader finns det?
Jämför definitionen av bankfilens layout med Finance and Operations-importdefinitionen, och notera eventuella skillnader i fält och element. Jämför bankutdragsfilen med relaterad Finance and Operations-exempelfil. Skillnader i ISO20022-filerna bör vara lätta att se.

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

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  Kopiera innehållet i bankutdragsfilen och klistra in det i XML-filen så att det ersätter **PASTESTATEMENTFILEHERE**.

### <a name="debug-the-xslt"></a>Felsöka XSLT

Mer information finns i <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.

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

Justera transformeringen för att få lämpligt fält eller element i bankutdragsfilen. Mappa sedan detta fält eller element med lämpligt Finance and Operations-element.

### <a name="debitcredit-indicator"></a>Debet-/kreditindikator

Ibland kan debet importeras som kredit, och kredit kan importeras som debet. För att lösa detta problem måste du ändra lämplig XSLT. Om bankutdrag kommer från flera banker, se då till att alla använder samma debet-/kreditmetod, eller skapa separata transformeringar.

-   BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator-mall
-   ISO20022XML-to-Reconcilation.xslt GetCreditDebit-mall
-   MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator-mall

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exempel på bankutdragsformat och tekniska layouter
Följande tabell anger exempel på tekniska layoutdefinitioner för importfiler för avancerade bankavstämningar, samt tre relaterade bankutdragsexempelfiler. Du kan hämta till exempelfiler och tekniska layouter här: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  


| Teknisk layoutdefinition                             | Bankutdragsexempelfil          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |






