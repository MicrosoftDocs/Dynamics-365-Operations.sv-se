---
title: "Lägga upp ett sortiment"
description: "Denna artikeln beskriver vad ett sortiment är och förklarar hur du ställer in sortiment i Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15811
ms.assetid: d2580048-e798-4b33-85f9-d1bad7d262fc
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 91713a4492ad82520f7dde611c17a5ea168ed80d
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-assortments"></a>Lägg upp sortiment

[!include [banner](includes/banner.md)]

Denna artikeln beskriver vad ett sortiment är och förklarar hur du ställer in sortiment i Microsoft Dynamics 365 for Retail.

Ett sortiment är en samling relaterade produkter som du tilldelar en butikskanal, till exempel en fysisk butik eller en onlinebutik. Du använder sortiment för att identifiera de produkter som är tillgängliga i varje butik. Ett sortiment kan inkludera kategorier av produkter. Alla produkter som tilldelats den valda kategorin, ingår i sortimentet. Ett sortiment kan också ta med specifika produkter och specifika varianter av produkter. Om du ställer in ett sortiment, kan du tilldela tusentals produkter till dina butikskanaler samtidigt, i valfri kombination som din butik kräver. Du kan ställa in så många produktsortiment, som du behöver. Varje produkt kan inkluderas i ett eller flera sortiment, och varje produkt kan tilldelas en eller flera butikskanaler. Om du till exempel anger ett sortiment som innehåller en basuppsättning med produkter. Alla butiker tar emot sortimentet. Du definierar sedan ett annat sortiment som inkluderar en större sportutrustning. Endast dina större butiker får sortimentet. Följande diagram visar hur produkter kan tilldelas sortiment, och hur de sortimenten kan tilldelas butikskanaler. ![Relationer för produktsortiment](./media/assortments_relationship.gif)

## <a name="prerequisites"></a>Krav
Innan du kan ställa in ett sortiment och tilldela den till en butikskanal, måste du göra följande.

| Uppgift                              | Beskrivning                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ställa in en butikskanal          | En butikskanal representerar den fysiska butiken, onlinebutiken och onlinemarknadsplatsen. Du måste ställa in minst en kanal och konfigurera alternativen för butiken. Sortiment tilldelas butikerna för att identifiera de produkter som en viss butik har.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Skapa en organisationshierarki. | När du har ställt in butikskanalerna för din organisation, måste du konfigurera en butiksorganisationshierarki som representerar organisationsstrukturen hos dina butikskanaler. Du kan använda organisationshierarkin för sortiment, påfyllnad eller rapportering. Genom att lägga till dina butikskanaler till en organisationshierarki kan du tilldela sortiment till grupper av butiker. Istället för att tilldela sortimentet individuellt för varje butik tilldelar du sortimentet i organisationnoden på hög nivå. Därefter, när en ny butikskanal läggs till i organisationnoden på hög nivå, kommer butikskanalen automatiskt att ärva de sortiment som har tilldelats i organisationnoden. Du kan bara tilldela sortiment för butikskanaler som är inkluderade i en organisationshierarki, som tilldelas syftet **Butikssortiment**. |
| Definiera produkter.                  | Innan du kan lägga till produkter till ett sortiment, måste du lägga till dem i Microsoft Dynamics 365 for Retail. Du kan lägga till produkter manuellt, eller så kan du importera dem från en leverantör. När du har lagt till produkterna, måste du frisläppa dem till en juridisk person. Endast produkter som har frisläppts till juridiska personer, kan göras tillgängliga för dina butikskanaler. Produkter, som ännu inte har frisläppts till en juridisk person, kan läggas till ett sortiment och sortimentet kan godkännas. Endast produkter som har frisläppts till juridiska personer, kan göras tillgängliga för dina butikskanaler.                                                                                                                                                                                                                                                                                     |
| Ställ in en kategorihierarki      | När du skapar dina butiksprodukter, kan du gruppera dem och kategorisera dem genom att använda kategorihierarkifunktionen. Du kan skapa en huvudhierarki för att gruppera och kategorisera alla produkter som du distribuerar via butikskanaler. Du kan också skapa separata extra kategorihierarkier för att gruppera eller kategorisera dina produkter för särskilda syften, till exempel kampanjer eller sortiment. Genom att använda kategorihierarkier, kan du tilldela alla produkter i en specifik kategori till ett sortiment. Vissa produkter som läggs till en kategori, som är inkluderade i sortimentet, inkluderas automatiskt i sortimentet. Nästa gång som butikssortimentplaneraren körs blir dessa produkter tillgängliga för de butikskanaler som sortimentet tilldelas.                                            |

## <a name="setting-up-an-assortment"></a>Ställa in ett sortiment
När du har slutfört förberedelserna, kan du skapa ett sortiment och tilldela den till dina butikskanaler. Om du vill ställa in ett sortiment måste du göra följande.

1.  Skapa ett nytt sortiment eller kopiera ett befintligt sortiment.
2.  Välj de butikskanalerna eller grupper med butikskanaler på hög nivå som sortimentet gäller för.
3.  Lägg till produktkategorier, enskilda produkter eller produktvarianter till sortimentet. Du kan inkludera alla produkter i en specifik kategori, eller så kan du utesluta valda produkter från en kategori som ingår i sortimentet.
4.  Publicera sortimentet. När du publicerar sortimentet kommer butikssortimentsschemaläggaren att köras automatiskt. Den här processen genererar listan med produkter. När den här processen slutförs blir produkterna tillgängliga för de butikskanaler som produktsortimentet tilldelas. Om ändringar görs i ett sortiment som har publicerats, eller till de butikskanalerna som sortimentet har tilldelats, måste sortimentet uppdateras. Om du vill uppdatera sortimentet när ändringar görs kan du köra en lämpligt sortimentplanerare som ett batchjobb.





