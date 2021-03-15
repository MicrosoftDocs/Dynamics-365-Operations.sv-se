---
title: Konfigurationer för leverantörsförfrågan
description: Det här avsnittet beskriver de fält som behöver ifyllas i en ny leverantörsförfrågan.
author: RichardLuan
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 987b9cefef395b3bf3e915f41232fe0daba213b9
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021175"
---
# <a name="vendor-request-configurations"></a>Konfigurationer för leverantörsförfrågan
[!include [banner](../includes/banner.md)]

Om du vill slutföra en leverantörsförfrågan måste en kontaktperson för leverantören slutföra registreringsguiden för potentiell leverantör.

I formuläret **Konfigurationer för leverantörsförfrågan** kan du skapa profiler som anger erforderliga och synliga fält i registreringsguiden för potentiell leverantör.

Registreringsguiden för leverantör börjar med att fråga den potentiella leverantörsanvändaren vilket land/vilken region leverantören är verksam i. Denna information bestämmer tillämpbar konfiguration. Om ingen specifik konfiguration definieras för ett land/en region kommer en standardkonfiguration att användas.

### <a name="set-up-a-vendor-request-configuration"></a>Skapa en konfiguration för leverantörsförfrågan

Som standard finns en leverantörskonfiguration i konfigurationsformuläret för leverantörsförfrågan.

Det går inte att välja länder/regioner för standardkonfigurationen, vilket innebär att avsnittet **Länder/regioner** inte kan ändras.

1. Klicka på **Anskaffning och inköp** > **Inställningar** > **Leverantörer**, och klicka sedan på **Konfigurationer för leverantörsförfrågan**.
2. Klicka på fliken **Fält** för att ange status för listade fält.
3. Dold (visas inte)
4. Visas (synlig men inte obligatorisk)
5. Obligatorisk (synlig och obligatorisk)
6. Klicka på fliken **Innehåll** för att ange om texten ska visas i guiden och om det ska finnas en bekräftelse att den potentiella leverantörsanvändaren måste acceptera detta innan han/hon fortsätter till nästa steg i guiden. Bekräftelsen kommer att begäras för alla villkor som användaren måste acceptera för att kunna fortsätta.

Du kan även ange ett bekräftelsemeddelande som visas när guiden har slutförts, och du kan lägga till en eller flera frågeformulär.

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a>Skapa en leverantörskonfiguration för ett visst land/en viss region
1.  Klicka på **Anskaffning och inköp** > **Inställningar** > **Leverantörer**, och klicka sedan på **Konfigurationer för leverantörsförfrågan**.
2.  Klicka på **Ny** för att skapa en ny konfiguration, och ange ett namn för konfigurationen.
3.  Klicka på **Spara**.
4.  Öppna fliken **Länder/regioner** för att välja det land/den region som konfigurationen ska användas för.
5.  Slutför konfigurationen genom att följa riktlinjerna för standardkonfigurationen.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]