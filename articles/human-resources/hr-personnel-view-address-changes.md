---
title: Visa och hantera adressändringar
description: I den här artikeln beskrivs hur du kan visa och hantera adressändringar i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-07
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 744ab532fcc663f25ce376817779924bbef15432
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899597"
---
# <a name="view-and-manage-address-changes"></a>Visa och hantera adressändringar


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I denna artikel beskrivs hur du kan visa och hantera adressändringar på sidan **Redigera personliga uppgifter** (som du öppnar via sidan **Självbetjäning för medarbetare**) eller informationssidan för **Medarbetare** i Dynamics 365 Human Resources.

Många företag vill att medarbetare ska hantera sina egna personliga uppgifter genom en självbetjäningsupplevelse. Du kan låta användarna uppdatera sin adress i arbetsytan **Självbetjäning för medarbetare**. Du kan sedan övervaka dessa ändringar i arbetsytan **personalhantering**. Om du vill använda den här funktionen måste du ange antalet dagar som du vill visa ändringar på sidan **personalparametrar**.

## <a name="configure-address-change-parameters"></a>Konfigurera parametrar för adressändring

Så här konfigurerar du det antal dagar som du vill att adressändringar ska visas i arbetsytan **personalhantering**:

1. Välj **personalhantering** i navigeringsfönstret.
2. Markera **länkar**
3. Välj **personalparametrar**.
4. I fältet **Antal dagar** under **adressändring**, anger du antalet dagar som du vill att adress ändringarna ska visas i arbetsytan **personalhantering**.
5. Stäng sidan.

## <a name="create-or-change-an-employee-address"></a>Skapa eller ändra en medarbetaradress

Medarbetare kan uppdatera sin adress i arbetsytan **Självbetjäning för medarbetare**. Följ dessa steg för att skapa eller ändra en adress:.

1. Välj panelen **Självbetjäning för medarbetare** på sidan **Start**.
2. Välj **redigera personuppgifter**.
3. Välj **Lägg till** om du vill lägga till en adress. Om du vill uppdatera en befintlig adress markerar du adressen från listan och väljer sedan **redigera**.
4. Ange **namn eller beskrivning**.
5. Välj listrutan **syfte** och välj sedan typ av adress.
6. Ange **land/region**.
7. Ange **postnumret**.
8. Ange **gatuadressen**.
9. Ange **ort**, **delstat** och **region**. Dessa fält ställs normalt automatiskt in utifrån fältet **postnummer**.
10. Du kan även välja det **primära** fältet om du vill ange en primär adress. Endast en adress kan markeras som primär. Om en annan adress redan har markerats som primär adress måste du bekräfta att du vill använda den här adressen som primär adress.
11. Du kan även välja det **Privat** fältet om du vill ange att en adress är privat. Endast användare med uttrycklig behörighet att visa privat adressinformation kan visa den här adressen.
12. Välj **OK**.

## <a name="create-or-change-a-worker-address"></a>Skapa eller ändra en adress till en arbetare

Du kan uppdatera en adress i arbetsytan **personalhantering**. Följ dessa steg för att skapa eller ändra en adress:.

1. I arbetsytan **personalhantering** välj **länkar** och välj sedan **arbetare**.
2. Välj anställd och klicka sedan på **Adresser**.
3. Välj **Lägg till** om du vill lägga till en adress. Om du vill uppdatera en befintlig adress markerar du adressen från listan och väljer sedan **redigera**.
4. Ange **namn eller beskrivning**.
5. Välj listrutan **syfte** och välj sedan typ av adress.
6. Ange **land/region**.
7. Ange **postnumret**.
8. Ange **gatuadressen**.
9. Ange **ort**, **delstat** och **region**. Dessa fält ställs normalt automatiskt in utifrån fältet **postnummer**.
10. Du kan även välja det **primära** fältet om du vill ange en primär adress. Endast en adress kan markeras som primär. Om en annan adress redan har markerats som primär adress måste du bekräfta att du vill använda den här adressen som primär adress.
11. Du kan även välja det **Privat** fältet om du vill ange att en adress är privat. Endast användare med uttrycklig behörighet att visa privat adressinformation kan visa den här adressen.
12. Välj **OK**.
 
## <a name="create-a-future-change-for-an-address"></a>Skapa en framtida ändring av en adress

I vissa fall kanske du vill uppdatera en adress för framtida ändringar. Det kan till exempel vara användbart om en medarbetare flyttas den 15 i följande månad.

1. Öppna sidan **Hantera adresser** genom att välja **fler alternativ > avancerat** i adressrutnät.
2. Skapa en ny adress genom att välja **Nytt**.
3. Ange detaljer för adress.
4. Välj snabbfliken **Allmänt**.
5. I fältet **giltighetsdatum** väljer du det datum då den nya adressen ska gälla.
6. I fältet **utgångsdatum** väljer du om adressen inte längre ska gälla.
7. Stäng sidorna.

## <a name="view-and-monitor-address-changes"></a>Visa och övervaka adressändringar

Personal kan visa och övervaka adressändringar från arbetsytan **personalhantering**. Om du vill visa adressändringarna väljer du panelen **Personalhantering** på sidan **Start**. Adressändringarna visas på en panel i det övre högra hörnet. Numret ovanför **Adressändringarna** visar hur många adressändringar som inträffat under det antal dagar som anges på sidan **Personalparametrar**. 

När du väljer panel **adressändringar** visas information om adressändringar på en ny sida. Du kan också välja att **Inkludera framtida adressändringar** i det övre högra hörnet för att visa adressändringar med ett framtida datum.

> [!NOTE]
> Om du vill få en notifiering eller skicka e-post om dessa adress ändringar, kan du skapa en ny notifieringsregel på fliken **Alternativ** i åtgärdsfönstret. Mer information om hur du skapar varningsregel finns i [Skapa varningsregel](../fin-ops-core/fin-ops/get-started/create-alerts.md).
>
> Om du vill konfigurera ett arbetsflöde för adressändringarna kan du välja alternativet **Skicka externt** i varningsregeln och sedan använda Power Automate för att utlösa affärshändelsen och konfigurera ett arbetsflöde. Mer information finns i [notifieringar som affärshändelser](../fin-ops-core/fin-ops/get-started/create-alerts.md#alerts-as-business-events).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
