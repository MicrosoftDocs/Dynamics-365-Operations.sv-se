---
title: Serviceobjektgrupper
description: Objektgrupper är användbara för att sortera och filtrera data om objekt för rapporter och statistik.
author: sorenva
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b53d51e4165797b176cfe70a8e25311e41d2999e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674769"
---
# <a name="service-object-groups"></a>Serviceobjektgrupper

[!include [banner](../includes/banner.md)]

Objektgrupper är användbara för att sortera och filtrera data om objekt för rapporter och statistik. Du kan exempelvis gruppera objekt efter geografisk placering eller typ.

## <a name="group-by-geographical-location"></a>Gruppera efter geografisk placering

Du kan använda den här grupperingsmetoden för att visa var olika objekt som ditt företag utför tjänster hos finns. Att gruppera objekt efter geografisk placering kan också vara användbart om du till exempel måste identifiera de objekt som ditt företag redan utför tjänster hos i ett visst land/region.

## <a name="example-of-grouping-by-geographical-location"></a>Exempel på gruppering efter geografiskt läge

En kund från Belgien ringer ditt servicecenter och vill skapa ett serviceavtal för ett objekt, ABC. Du har kopplat en objektgrupp med den geografiska placeringen "Belgien" till alla objekt som företaget utför service hos i Belgien. Genom att filtrera efter den här gruppen kan du snabbt ta reda på om ABC redan finns som en post i programmet eller om du måste skapa ett nytt objekt.

## <a name="group-by-type"></a>Gruppera efter typ

Du kan använda den här grupperingsmetoden för att visa vilka typer av objekt som ditt företag utför tjänster hos. Att gruppera objekt efter typ kan också vara praktiskt om du exempelvis vill skapa ett nytt objekt baserat på liknande objekt som redan finns i programmet.

## <a name="example-of-grouping-by-type"></a>Exempel på gruppering efter typ

En kund ringer och vill skapa ett serviceavtal för en luftkonditioneringsmaskin, HIJ. Du har inte en post för den här maskinen ännu. Men du har ställt in en objektgrupp som heter luftkonditioneringsapparater och du har kopplat den här gruppen till alla sådana objekt. Därför kan du snabbt söka efter och identifiera alla andra luftkonditioneringsapparater och använda mallinformationen från de här objekten för att skapa serviceavtalsrader för HIJ. Genom att använda objektgrupper på det här sättet sparar du tid när du skapar nya objekt och avgör vilka serviceuppgifter som ska utföras på dem.

## <a name="create-service-object-groups"></a>Skapa en serviceobjektgrupp

Skapa grupper som du kan tilldela till serviceobjekt till. Serviceobjekt är lagerartiklar andra produkter som tjänster utförs för. Genom att gruppera serviceobjekt kan du skapa rapporter för liknande och relaterade serviceobjekt. En serviceobjektgrupp kan till exempel bestå av två serviceobjekt: Ett serviceobjekt är ett paket och det andra serviceobjektet är tjänsten för att installera paketet.

Om du vill skapa serviceobjektgrupper, följ dessa steg:

1. Klicka på **servicehantering > inställningar > serviceobjekt > serviceobjektgrupper**.

2. Klicka på **Ny** om du vill skapa en ny serviceobjektgrupp.

3. Ange ett unikt namn på serviceobjektgruppen och eventuellt en beskrivning.

Du kan tilldela serviceobjekt till gruppen med hjälp av formuläret **Serviceobjekt**. 

## <a name="see-also"></a>Se även

[Skapa serviceobjekt](create-service-objects.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]