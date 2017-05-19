---
title: "Avancerad MT940-import för bankavstämning - uppgradering för sammansatt dataenhet"
description: "Ett sekvensnummer måste läggas till bankutdragimportenheten för att stödja MT940-formatet."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 3d44b6eb90d02844b283d7bc861b325357e3bd68
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Avancerad MT940-import för bankavstämning - uppgradering för sammansatt dataenhet

[!include[banner](../includes/banner.md)]


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
            -   Klicka på **Visa karta**.
            -   Klicka på **Visa karta** på bankutdragsdokumentet.
            -   Klicka på **Transformeringar**
            -   Ta bort filen BankReconiliation-to-Composite.xslt.
            -   Lägg till den nya versionen av BankReconiliation-to-Composite.xsl.

        2.  Visa layouten **Löpnummer** på **Källdata**.
            1.  Källdataformat = XML-Element.
            2.  Enhetsnamn = Bankutdrag.
            3.  Överföra datafil = ny version SampleBankCompositeEntity.xml.
            4.  Klicka på **Ja** om du vill skriva över den befintliga filen.
            5.  Klicka på **Ja** om du vill generera en ny mappning.
            6.  Kontrollera att S**equenceNumber** mappas.
                -   Klicka på **Visa karta** på bankutdraget.
                -   Kontrollera att **SequenceNumber** mappas från Källa till Mellanlagring.

3.  Importera det nya utdraget.





