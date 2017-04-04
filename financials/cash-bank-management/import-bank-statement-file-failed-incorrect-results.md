---
title: "Bankens kontoutdrag filen Felsöka importer"
description: "Det är viktigt att bankutdragsfilen från banken matchar layouten som stöder Microsoft Dynamics 365 för operationer. På grund av de strikta standarder som gäller för bankutdrag kommer de flesta integreringar att fungera korrekt. Ibland kan emellertid utdragsfilen inte importeras, eller också har den felaktiga resultat. Vanligtvis orsakas dessa problem av små skillnader i bankutdragsfilen. Denna artikel förklarar hur du korrigerar dessa skillnader och löser problemen."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eab840b2974f4e9e8cf542c146482ba8e4239079
ms.openlocfilehash: 9717cf2f36033efe8465906324966242977c6eb2
ms.lasthandoff: 03/31/2017


---

# <a name="bank-statement-file-import-troubleshooting"></a>Bankens kontoutdrag filen Felsöka importer

Det är viktigt att bankutdragsfilen från banken matchar layouten som stöder Microsoft Dynamics 365 för operationer. På grund av de strikta standarder som gäller för bankutdrag kommer de flesta integreringar att fungera korrekt. Ibland kan emellertid utdragsfilen inte importeras, eller också har den felaktiga resultat. Vanligtvis orsakas dessa problem av små skillnader i bankutdragsfilen. Denna artikel förklarar hur du korrigerar dessa skillnader och löser problemen.

<a name="what-is-the-error"></a>Vad består felet av?
------------------

Gå till jobbhistoriken för datahantering och dess utförandedetaljer för att hitta felet när du försöker importera en bankutdragsfil. Felet kan hjälpa dig genom att peka på utdraget, saldot eller utdragsraden. Det ger dig emellertid troligtvis inte tillräckligt med information för att hjälpa dig att identifiera det fält eller element som orsakat problemet.

## <a name="what-are-the-differences"></a>Vilka skillnader finns det?
Jämför Layoutdefinitionen bank-fil till Microsoft Dynamics 365 operationer importen definition och anteckna skillnaderna i fält och element. Jämför bankutdragsfilen relaterade exemplet Dynamics 365 för operationer. Skillnader i ISO20022-filerna ska vara lätt att se.

## <a name="transformations"></a>Transformeringar
Normalt måste ändringen utföras i en av de tre transformeringarna. Varje transformering skrivs för en viss standard.

| Resursnamn                                         | Filnamn                          |
|-------------------------------------------------------|------------------------------------|
| BankStmtImport\_BAI2CSV\_till\_BAI2XML\_xslt            | BAI2CSV-to-BAI2XML.xslt            |
| BankStmtImport\_ISO20022XML\_till\_avstämning\_xslt | ISO20022XML-to-Reconciliation.xslt |
| BankStmtImport\_MT940TXT\_till\_MT940XML\_xslt          | MT940TXT-to-MT940XML.xslt          |

## <a name="debugging-transformations"></a>Felsökningtransformeringar
### <a name="adjust-the-bai2-and-mt940-files"></a>Justera filerna BAI2 och MT940

Filerna BAI2 och MT940 är textbaserade filer och kräver en justering om du vill aktivera felsökning för Extensible Stylesheet Language-transformeringar (XSLT). Programmet utför denna justering när en fil importeras.

1.  Skapa en XML-fil och kopiera följande text till den.

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  Kopiera innehållet i bankutdragsfilen och klistra in det i XML-filen så att det ersätter **PASTESTATEMENTFILEHERE**.

### <a name="debug-the-xslt"></a>Felsöka XSLT

Mer information finns på <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.

1.  Starta Microsoft Visual Studio.
2.  Skapa en konsolapplikation.
3.  Öppna lämplig XSLT.
4.  Klicka på XLST:n och dess egenskapssida.
5.  Ange inmatningen på platsen för bankutdragsfilen.
6.  Definiera en plats och ett filnamn för utdatan.
7.  Ange erforderliga brytpunkter.
8.  Klicka på på-menyn **XML**&gt;**Starta felsökning XSLT-**.

### <a name="format-the-xslt-output"></a>Formatera XSLT-utdata

När transformeringen körs skapas en utdatafil som du kan visa i Visual Studio. Använd Ctrl+A, Ctrl+K och Ctrl+D för att snabbformatera utdatafilen.

### <a name="adjust-the-transformation"></a>Justera transformeringen

Justera transformeringen för att få lämpligt fält eller element i bankutdragsfilen. Mappa fältet eller elementet till lämplig Dynamics 365 för operationer element.

### <a name="debitcredit-indicator"></a>Debet-/kreditindikator

Ibland kan debet importeras som kredit, och kredit kan importeras som debet. För att lösa detta problem måste du ändra lämplig XSLT. Om bankutdrag kommer från flera banker, se då till att alla använder samma debet-/kreditmetod, eller skapa separata transformeringar.

-   BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator-mall
-   ISO20022XML-to-Reconcilation.xslt GetCreditDebit-mall
-   MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator-mall

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exempel på bankutdragsformat och tekniska layouter
Följande tabell anger exempel på tekniska layoutdefinitioner för importfiler för avancerade bankavstämningar, samt tre relaterade bankutdragsexempelfiler. Du kan hämta till exempel filer och tekniska layouter här: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  


| Teknisk layoutdefinition                             | Bankutdragsexempelfil          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |



