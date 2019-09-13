---
title: Användargränssnittselement
description: I det här avsnittet beskrivs de användargränssnittselement som används i Dynamics 365 for Finance and Operations.
author: ''
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: ''
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: b9ba0dce29c7569a3eefcf1e07238f19644ecdf0
ms.sourcegitcommit: 6545bef4584d72dd7789f2d3935cf00ac8f489b0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2019
ms.locfileid: "1871097"
---
# <a name="user-interface-elements"></a>Användargränssnittselement

I det här avsnittet beskrivs de användargränssnittselement som används i Dynamics 365 for Finance and Operations. Innan användarna kan navigera i gränssnittet är det viktigt att känna till namn och funktioner för de element som utgör gränssnittet.

## <a name="overview"></a>Översikt

- **Åtgärdsfönster** – fältet under navigeringsfältet. Här kan du välja flikar för att ändra vilka poster som visas på sidan. Du kan redigera och spara posterna här.  
- **Faktabox** – du kan visa information och följa alla aktiviteter för vissa poster i det här fönstret.  
- **Faktaboxruta** fönstret där kan du bläddra igenom olika aspekter av en post som du vill visa i faktaboxen.  
- **Filterfönstret** – på vissa sidor kan du välja **Visa filter** om du vill öppna fönstret. Du kan begränsa resultaten som visas på sidan.  
- **Navigeringsfält** – fältet högst upp i gränssnittet. Det innehåller **Dynamics 365-portalen**, **Sök**, **företagsväljare**, **åtgärdscenter**, **Inställningar**, **Hjälp och Support** och användarprofilen.  
- **Navigeringslista** – på vissa sidor kan du bläddra genom det här fönstret om du vill söka efter en viss post. När det här alternativet väljs visas information om posten på sidan.  
- **Navigeringsfönster** – fönstret längst till vänster. Härifrån kan du hitta alla sidor i produkten.  
- **Sida** – Centralt fokus för gränssnittet. Val som görs på andra komponenter i användargränssnittet påverkar vilka poster som visas här.  
- **Fönster** – rutan längst till höger. Detta öppnas i vissa fall när aspekter av en post måste ändras och sparas.  
- **Flik** -när du refererar till åtgärdsfönstret visas en meny med alternativ som visas när du väljer ett alternativ i åtgärdsfönstret.  

![Följande bild visar placeringen av elementen i gränssnittet.](media/user-interface-01.png)

## <a name="tabs-fields-and-sections"></a>Flikar, fält och avsnitt

En *flik* är ett val som görs på sidan och som öppnar en annan aspekt av en post på samma sida. Ofta kan du ändra vissa *fält* eller gränssnittselement som tillåter skrivna indata. 

En *snabbflik* är en flik med den extra fördelen att flera flikar är synliga samtidigt. Du kan expandera en snabbflik genom att välja den nedåtriktade pilen till höger i slutet av den.

![I bilden nedan visas ett exempel på flikar och snabbflikar.](media/user-interface-02.png)

Ett *avsnitt* liknar en flik. Ordet "avsnitt" används ofta för att beskriva ett område på en sida som strukturerar en viss informationskategori. I följande bild är sammanfattningar, order och favoriter och länkar exempel på avsnitt.

![I bilden nedan visas ett exempel på flikar och ett avsnitt.](media/user-interface-03.png)

## <a name="dialog-boxes-and-drop-down-menus"></a>Dialogrutor och nedrullningsbara menyer

En *dialogruta* är ett fönster som öppnas när vissa val görs för att ändra eller skapa en post. Dialogrutor innehåller fält där du kan ange skrivna indata. Ibland kan du med ett angivet fält välja en nedåtriktad pil som öppnar en lista med alternativ som du kan välja mellan. Detta kallas för en *nedrullningsbar meny*. I följande bild innehåller fälten **Typ** och **Kundgrupp** alternativet att öppna en nedrullningsbar meny.

![I bilden nedan visas ett exempel på en dialogruta.](media/user-interface-04.png)

I vissa fall öppnas en dialogruta bredvid en given knapp när du väljer den. Detta kallas för en *nedrullningsbar dialogruta*. I bilden nedan har knappen **Från och med (datum)** valts, som öppnar en nedrullningsbar dialogruta.

![I bilden nedan visas ett exempel på en nedrullningsbar dialogruta.](media/user-interface-05.png)

## <a name="notifications"></a>Meddelanden

Vissa ändringar av de objekt du övervakar visas som *meddelanden.* Ett meddelande kan visas när en specifik kunds information har ändrats, eller så får du en varning när systemet inte kan ta emot inmatningar som du har lagt till i vissa fält. Du kan lära dig hur du anpassar vad du får meddelanden om i [Översikt över notifieringar](../get-started/alerts-overview.md).

Meddelanden visas på flera olika sätt.
- **Bildtext för funktioner** – det här visas vid ett fält, en flik eller någon annan knapp för att ge en förklaring till vad funktionen används till. 
- **Åtgärdscenter** – en ruta som innehåller meddelandet visas bredvid knappen åtgärdscenter i navigeringsfältet. Du kan visa detaljer om meddelandet genom att välja **åtgärdscentret**.  
- **Meddelandefält** – denna visas under åtgärdsfönstret.  

Följande bild visar exempel på dessa typer av meddelanden.

![Följande bild visar exempel på meddelanden.](media/user-interface-06.png)

- **Meddelanderuta** – detta kommer att visas över gränssnittet och måste samverkas med innan du kan fortsätta att använda produkten.  

![I bilden nedan visas ett exempel på en meddelanderuta.](media/user-interface-07.png)

## <a name="toolbars-grids-and-lists"></a>Verktygsfält, rutnät och listor

Ett *verktygsfält* innehåller verktyg, t.ex. möjligheten att lägga till fält eller ta bort poster. Ibland visas ett verktygsfält på sidan ovanför ett *rutnät.* Det här området, rutnät, är ett namn på rader med poster som har olika kolumner med data. Vissa rutnät har inte några verktygsfält ovanför.

En *lista* är det namn som ges till en samling poster som du kan rulla igenom. Du kan flytta dessa poster till sidan genom att markera dem. Detta öppnar ofta ett rutnät.

![Följande bild visar exempel på verktygsfält, rutnät och listor.](media/user-interface-08.png)
