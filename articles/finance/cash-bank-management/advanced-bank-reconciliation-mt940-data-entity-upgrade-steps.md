---
title: Avancerad MT940-import för bankavstämning – uppgradering för sammansatt dataenhet
description: Ett sekvensnummer måste läggas till bankutdragimportenheten för att stödja MT940-formatet.
author: angelad116
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e0cf603e04be4f8f784a32b9ef98d748d4d28e5b
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151504"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Avancerad MT940-import för bankavstämning – uppgradering för sammansatt dataenhet

[!include [banner](../includes/banner.md)]

Ett sekvensnummer måste läggas till bankutdragimportenheten för att stödja MT940-formatet. 

Använd följande steg när du vill lägga till bankutdragimportenheten för att stödja MT940-formatet.

1.  Kompilera och synkronisera följande:
    -   Sammansatt enhet\\BankStatementImportEntity
    -   Enhet\\BankStatementBalanceEntity
    -   Enhet\\BankStatementDocumentEntity
    -   Enhet\\BankStatementEntity
    -   ENhet\\BankStatementLineEntity
    -   Register\\BankStatementStaging

2.  Datahantering\\dataprojekt.
    1.  Läs in MT940-importprojekt
        1.  Ändra XSLT.
            -   Klicka på **Visa mappning**.
            -   Klicka på **Visa mappning** på bankutdragsdokumentet.
            -   Klicka på **Transformeringar**
            -   Ta bort filen BankReconiliation-to-Composite.xslt.
            -   Lägg till den nya versionen av BankReconiliation-to-Composite.xsl.

        2.  Visa layouten **Löpnummer** på **Källdata**.
            1.  Källdataformat = XML-Element.
            2.  Enhetsnamn = Bankutdrag.
            3.  Överföra datafil = ny version SampleBankCompositeEntity.xml.
            4.  Klicka på **Ja** om du vill skriva över den befintliga filen.
            5.  Klicka på **Ja** om du vill generera en ny mappning.
            6.  Kontrollera att S **equenceNumber** mappas.
                -   Klicka på **Visa mappning** på bankutdraget.
                -   Kontrollera att **SequenceNumber** mappas från Källa till Mellanlagring.

3.  Importera det nya utdraget.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
