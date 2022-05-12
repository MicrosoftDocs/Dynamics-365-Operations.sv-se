---
title: Konfigurera e-fakturering
description: Detta ämne ger en översikt över processen för att ställa in och konfigurera e-fakturering.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 42e617e26e7658fae9ee54cb8a4dee45314fddaa
ms.sourcegitcommit: 5f7177b9ab192b5a6554bfc2f285f7cf0b046264
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2022
ms.locfileid: "8661704"
---
# <a name="electronic-invoicing-setup"></a>Konfigurera e-fakturering

[!include [banner](../includes/banner.md)]

Ämnet ger en översikt över processen för att ställa in och konfigurera e-fakturering. Du måste utföra inställningsstegen i den ordning som anges här. Om ett steg är obligatoriskt men du hoppar över det fungerar inte funktionen på rätt sätt, och flera fel kommer att uppstå under efterföljande steg eller när du använder funktionen. 

Innan du börjar ska du kontrollera att alla huvudkomponenter har ställts in på rätt sätt, att du har registrerat dig för Regulatory Configuration Service (RCS) och har en instans av RCS, samt att tillägget för e-fakturering är installerat för din Microsoft Microsoft Dynamics 365 Finance eller Dynamics 365 Supply Chain Management-miljö. För mer information, se [Registrera dig och installera e-fakturering](e-invoicing-install-add-in-microservices-lcs.md).

Ställ sedan in de Azure-resurser som e-fakturering kräver för att kunna uträtta sitt arbete. För mer information, se [Konfigurera Azure-resurser för e-fakturering](e-invoicing-set-up-azure-resources.md).

När huvudkomponenterna har konfigurerats bör du arbeta med RCS för att ställa in de huvudsakliga logiska komponenterna för e-fakturering. Definiera först antalet tjänstemiljöer som du ska underhålla. På det här sättet definierar du den logiska data- och konfigurationspartitionen för att säkerställa att du har en gräns mellan en utvecklings- eller testmiljö och produktionsmiljöerna. Om du vill ställa in din utvecklingsprocess på ett flexibelt sätt kanske du behöver flera separata utvecklings- och testmiljöer. Förutom att definiera servicemiljöer ställer du in en länk till dina affärsprogram, till exempel Ekonomi eller Supply Chain Management, direkt från RCS för att ställa in de parametrar som behövs för att e-fakturering ska fungera korrekt. Mer information om miljöer finns i [tjänstemiljöer](e-invoicing-service-environments.md).

När allt har ställts in kan du skapa egna globaliseringsfunktioner som anger olika scenarier för bearbetning av elektroniska dokument och transformering av data, eller för import av dokument från den globala databasen. Mer information om hur du arbetar med globaliseringsfunktioner finns i [Arbeta med globaliseringsfunktioner](e-invoicing-working-globalization-features.md).

Om dina scenarier kräver integrering med e-post eller SharePoint för att bearbeta inkommande elektroniska dokument, se [Bearbeta inkommande elektroniska domument](e-invoicing-process-incoming-electronic-documents.md) för att få information om om hur du ställer in och använder dessa kanaler.
