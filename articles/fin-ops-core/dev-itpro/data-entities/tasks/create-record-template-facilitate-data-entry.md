---
title: Skapa en postmall för att förenkla datainmatning
description: Det här avsnittet visar hur du skapar en postmall så att fältvärden som ofta används inte uttryckligen behöver anges för varje ny post.
author: margoc
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 08ee7d0f0ce7e92eaa85137dcd2761bfd702eb8c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181943"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a>Skapa en postmall för att förenkla datainmatning

[!include [task guide banner](../../includes/task-guide-banner.md)]

Det här avsnittet visar hur du skapar en postmall så att fältvärden som ofta används inte uttryckligen behöver anges för varje ny post. I den här proceduren ska du skapa en ny post för nya bärbara datorer som ska läggas till bland anläggningstillgångarna. I den här proceduren används demonstrationsföretaget USMF.

1. I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Anläggningstillgångar > Anläggningstillgångar**.
2. Välj **Ny**.
3. Ange eller välj ett värde i fältet **Anläggningstillgångsgrupp.**
4. Skriv ett värde i fältet **Namn**. Ange till exempel **Bärbar dator för företags-lead**.  
5. Ange ett värde i fältet **Söknamn**. Ange till exempel **bärbar dator**.  
6. Expandera avsnittet **Teknisk information**.
7. Ange värden i fälten **Fabrikat**, **Modell** och **Modellår**.
8. Välj **Alternativ** i åtgärdsfönstret.
9. Välj **Postinfo**.
10. Välj **Användarmall**.
11. Skriv ett värde i fältet **Namn**.
12. I fältet **Beskrivning** anger du ett värde.
13. Välj **OK**.
14. Välj **Nära**.
