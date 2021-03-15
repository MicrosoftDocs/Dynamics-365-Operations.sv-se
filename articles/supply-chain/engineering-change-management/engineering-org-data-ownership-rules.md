---
title: Regler för teknikföretag och dataägande
description: I det här avsnittet beskrivs hur du kan använda ett eller flera teknikföretag för att se till att huvuddata för produkter skapas och underhålls centralt. Ett teknikföretag representerar det företag som äger de tekniska produkterna och det är dess tekniska data.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgEngineeringOrganization
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: ab5ca3bee65bb0ee8ce7f44ba97c00347fe38366
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963673"
---
# <a name="engineering-companies-and-data-ownership-rules"></a>Regler för teknikföretag och dataägande

[!include [banner](../includes/banner.md)]

## <a name="engineering-companies-and-operational-companies"></a>Teknikföretag och operativa företag

För att säkerställa att huvuddata för produkter skapas och underhålls centralt kan du använda en eller flera *teknikföretag*. Ett teknikföretag äger ingenjörsprodukterna och deras tekniskt relevanta data. Den är alltid ansluten till (baserad på) en befintlig *juridisk person*, som också är ett företag. Genom den här anslutningen upprättar systemet en central startpunkt för alla tekniska relevanta data för tekniska produkter i det tekniska företaget. I den här centrala startpunkten skapas teknikprodukter och tekniska relevanta data upprätthålls. Därifrån kommer de tekniska produkter och tekniska data att frisläppas på *operativa företag*, som är andra juridiska personer. (Mer information om den frisläppningshanteringen finns i [Frisläpp produktstrukturer](release-product-structure.md)). Dessa operativa företag kommer att använda de tekniska data som de har konstruerats av det tekniska företaget. Alla logistiska data hanteras lokalt av varje tekniskt företag och operativa företag.

Om du vill skapa ett tekniskt företag går du till **Konstruktionsändringshantering \> Inställningar \> Tekniska organisationer**. Välj **ny**, ange ett namn på tekniska företaget och välj det befintliga företag (juridisk person) som det är baserat på.

Om du integrerar med externa PLM-system (Product Lifecycle Management) måste du skapa en affärsenhet (typ av företag) som blir ett externt företag.

## <a name="engineering-product-categories-and-engineering-companies"></a>Produktkategorier för teknik och ingenjörsföretag

*Produktkategorier för teknik* hjälpa till att säkerställa att tekniska produkter skapas enligt ditt företags affärsregler och beter sig efter behov. Mer information om tekniska produktkategorier finns i [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).

Varje teknisk produktkategori tillhör ett specifikt tekniskt företag och kan bara skapa produkter som tillhör företaget. På samma sätt hör rätten att underhålla en teknisk produkt även till det företag som är associerat med produktens tekniska produktkategori.

## <a name="data-that-is-owned-by-the-engineering-company"></a>Data som ägs av teknik företaget

Eftersom det tekniska företaget äger tekniskrelevanta data, styr den följande processer:

- **Skapande av tekniska produkter:** varje tekniskt företag kan bara skapa nya konstruktionsprodukter som bygger på en teknisk produktkategori som den äger. I vissa fall behåller operativa företagen sina egna lokala data som är relaterade till dessa produkter.
- **Skapa konstruktionsversioner:** när ett företag skapar en ny teknisk produkt, skapar systemet automatiskt en första konstruktionsversion för den. Endast det ägande tekniska företaget kan skapa nya versioner av produkten.
- **Skapa och underhålla tekniska attribut:** När ett företag skapar en ny teknisk produkt lägger systemet automatiskt till tekniska attribut till den. Endast det ägande tekniska företaget kan skapa och underhålla värdena för dessa attribut. De tekniska attributen (mer information finns i [Tekniska attribut och sökning efter tekniska attribut](engineering-attributes-and-search.md)).
- **Skapa och underhålla strukturlistor som är anslutna till teknik versionerna:** det ägande tekniska företaget kan direkt ansluta en strukturlista till en teknisk produktversion. När strukturlistorna frisläpps till andra juridiska personer begränsas ändringar av tekniska data i strukturlistorna på följande sätt:

    - Det operativa företaget kan inte ta bort släppta strukturlisterader.
    - Teknik fälten på strukturlisteraderna är skrivskyddade för det operativa företaget. Alla andra fält är logistiska implementeringsfält och kan redigeras av det operativa företaget.
    - Det operativa företaget kan lägga till strukturlisterader till samma strukturlista. På så sätt kan den lägga till lokala tillägg, t.ex. förpackningsmaterial eller smörjvätska.
    - Det operativa företaget kan lägga till en helt ny, lokal strukturlista. Denna ändring kan krävas om det t.ex. inte finns någon strukturlista under frisläppandet. Det operativa företaget äger och underhåller dessa lokala strukturlistor. Mer information om frisläppningshantering finns i [Frisläpp produktstrukturer](release-product-structure.md).
    - Alla lokala strukturlistor och strukturlisterader behålls när det tekniska företaget uppdaterar sin strukturlista.

- **Skapa och underhålla flöden som är anslutna till teknik versionerna:** det ägande tekniska företaget kan direkt ansluta ett flöde till varje teknisk produktversion. När dessa flöden frisläpps till andra juridiska personer begränsas ändringar av flöden på följande sätt:

    - De andra juridiska personerna kan inte ta bort tekniska data på flödena.
    - De andra juridiska personerna kan lägga till operationer i flödet. På så sätt kan de lägga till lokala flödessteg.
    - Operativa företag kan lägga till helt nya, lokala flöden. Denna ändring kan krävas om du till exempel inte har inkluderat flöden under frisläppandet. Det operativa företaget äger och underhåller dessa lokala flöden. Mer information om frisläppningshantering finns i [Frisläpp produktstrukturer](release-product-structure.md).
    - Alla ändringar som görs lokalt bevaras när uppdateringarna från tekniska företaget släpps igen på flödena.

- **Skapande och underhåll av tekniska dokument:** det tekniska företaget kan bifoga tekniska dokument till varje teknisk version.

    - När dessa dokument frisläpps till andra juridiska personer, skyddas dokumenten från att tas bort av operativa företaget.
    - Andra juridiska personer kan lägga till helt nya lokala dokument. Det operativa företaget äger och underhåller dessa lokala dokument.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]