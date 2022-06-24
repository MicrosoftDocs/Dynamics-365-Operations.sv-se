---
title: Konfigurationer för leverantörsförfrågan
description: Denna artikel beskriver de fält som behöver ifyllas i en ny leverantörsförfrågan.
author: GalynaFedorova
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 0f583caaaf4909918fafc0e8ef08490e25057561
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890869"
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