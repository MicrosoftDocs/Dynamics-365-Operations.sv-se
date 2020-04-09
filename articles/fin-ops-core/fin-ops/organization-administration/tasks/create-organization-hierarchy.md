---
title: Skapa en organisationshierarki.
description: Använd följande procedur för att skapa en organisationshierarki.
author: sericks007
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMHierarchyPurposeAssociation, OMHierarchySelection, HierarchyDesigner
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dde06f758be57fb646696c861218565476abcadc
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140569"
---
# <a name="create-an-organization-hierarchy"></a>Skapa en organisationshierarki.

[!include [banner](../../includes/banner.md)]

Använd följande procedur för att skapa en organisationshierarki. Du kan använda organisationens hierarkier för att visa och skapa en rapport från olika perspektiv av din verksamhet. Du kan till exempel skapa en hierarki för momsrapportering, juridisk rapportering eller lagstadgad rapportering. Du kan ställa in en annan hierarki om du vill rapportera ekonomisk information som inte krävs lagligen, men som används för intern rapportering. 

Innan du skapar en organisationshierarki måste du skapa organisationer. Mer information finns i uppgifterna "Skapa en juridisk person” eller ”Skapa en driftenhet”. Du kan också skapa avdelningar och team. 

Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

## <a name="create-a-hierarchy"></a>Skapa en hierarki
1. Gå till **Navigeringsfönster > Moduler > Organisationsadministration > Organisationer > Organisationshierarkier**.
2. Klicka på **Nytt** i **Åtgärdsfönstret**.
3. Skriv ett värde i fältet **Namn**.
4. I avsnittet **Syfte**, klicka på **Tilldela syfte**.
5. Hitta och markera önskad post i listan. Välj ett syfte att tilldela till din organisationshierarki.  
6. Klicka på **Lägg till** i avsnittet **Tilldelade hierarkier**.
7. Markera vald rad i listan. Hitta hierarki som du just skapat.  
8. Klicka på **OK**.

## <a name="add-organizations-to-the-hierarchy"></a>Lägg till organisationer i hierarkin
1. Hitta och markera önskad post i listan. Välj hierarki.  
2. Klicka på **Visa hierarki** i avsnittet **Tilldelade hierarkier**.
    - Lägg till fler organisationer efter behov.  
    - Klicka på **Redigera** och sedan **Infoga** om du vill lägga till en organisation. När du är klar med ändringar, kan du **spara** ett utkast och/eller **publicera** ändringarna.  

