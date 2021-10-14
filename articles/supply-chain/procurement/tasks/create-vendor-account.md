---
title: Skapa ett leverantörskonto
description: I den här proceduren visas hur du skapar ett leverantörskonto och lägger till en adress och kontaktinformation.
author: Henrikan
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16abc34b881fffdb9f278fd097efbcdc693b235f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570355"
---
# <a name="create-a-vendor-account"></a>Skapa ett leverantörskonto

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar ett leverantörskonto och lägger till en adress och kontaktinformation. I proceduren visas inte hur du fyller i alla fält i inköpssyfte och ekonomiska syften. Läs fältbeskrivningarna om du vill veta mer om dessa fält. Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Leverantörkonton skapas vanligtvis av ett anskaffningsproffs eller en kundreskontrapersonal.


## <a name="create-a-vendor-account"></a>Skapa ett leverantörskonto
1. Gå till **navigeringsfönstret > Moduler > Anskaffning och källa > Leverantörer > Alla leverantörer**.
2. Klicka på **Ny**.
3. I fältet **Leverantörskonto**, skriv ett värde.
    - Värdet kan fyllas i automatiskt. Om det gör det kan du hoppa över det här steget.  
    - Du kan skapa leverantörskonton för en person eller en organisation. Detta påverkar vilka fält som är tillgängliga. I det här exemplet ska du skapa ett leverantörskonto för en organisation.   
4. I fältet **Namn** anger eller väljer du ett värde. Om leverantören är en redan registrerad part i systemet kan du använda listrutan och välja honom/henne i det här fältet, så ärver det nya leverantörskontot den adress och kontaktinformation som redan är registrerad.
5. Ange eller välj ett värde i fältet **Grupp**. Leverantörsgruppen används för att gruppera leverantörer som har någon av följande parametrar gemensamt: Betalningsvillkor, kvittningsperiod, huvudbokskonton för lagerbokföring inklusive momsgruppen, standardhuvudbokskonton, produktfilterkoder och leveransprognoskonfiguration.
6. Ange ett antal i fältet **Antal medarbetare**.
7. Skriv ett värde i fältet **Organisationsnummer**.

## <a name="add-an-address"></a>Lägg till en adress
1. Expandera avsnittet **Adresser**.
2. Klicka på **Lägg till**.
3. Ange eller välj ett värde i fältet **Syfte**. Du kan välja en eller flera syften. Dessa används för att välja korrekt adress för ett visst syfte. Om syftet t.ex. är "Faktura" kommer den adressen att användas när du skickar fakturor.
4. Skriv ett värde i fältet **Namn eller beskrivning**.
5. Ange eller välj ett värde i fältet **Land/region**. Ange adressinformationen. Landet/regionen som du har valt bestämmer vilka fält som du presenteras tillsammans med, vilket motsvarar adressformatet för landet/regionen. 
6. Klicka på **OK**.

## <a name="add-contact-information"></a>Lägg till kontaktinformation
1. Expandera avsnittet **Kontaktinformation.**
2. Klicka på **Lägg till**.
3. I fältet **Beskrivning** anger du ett värde.
4. Välj ett alternativ i fältet **Typ**.
5. Skriv ett värde i fältet **Kontaktens nummer/adress**. Du kan markera den kryssrutan Primär om detta är den primära kontakten.  
6. Klicka på **Spara**.
7. Stäng sidan.
8. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]