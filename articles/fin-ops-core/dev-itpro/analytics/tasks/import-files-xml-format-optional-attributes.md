---
title: (RCS) Importera filer i XML-format med valfria attribut
description: Det här avsnittet innehåller information om hur en användare kan utforma ER-formatkonfiguration för import av filer i XML-format som innehåller valfria attribut.
author: NickSelin
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1d4c8c1d81faa60193d2339fd6541e752c2e2f9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684149"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a>(RCS) Importera filer i XML-format med valfria attribut

[!include [banner](../../includes/banner.md)]

I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan designa ER-formatkonfiguration att importera filer i XML-format med valfria attribut. För att slutföra dessa steg måste du först slutföra stegen i proceduren "Create a configuration provider and mark it as active”. Innan du börjar hämtar du filen IncomingDocumentToLearnHowToHandleOptionalAttributes.xml från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684) och sparar den lokalt.

1.    Gå till **Alla arbetsytor** > **Elektronisk rapportering**.
2.    Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren [Skapa konfigurationsleverantörer och välj dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md).
3.    Klicka på **Rapporteringskonfiguration**.

## <a name="create-a-new-data-model-configuration"></a>Skapa en ny datamodellskonfiguration
1.    Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.
2.    I fältet **Namn** skriver du "Model to import xml file".
3.    Klicka på **Skapa konfiguration**.
4.    Klicka på **Designer**.
5.    Klicka på **Nytt** om du vill öppna dialogrutan.
6.    Ange "Root" i fältet **Namn**.
7.    Klicka på **Lägg till**.
8.    Klicka på **Nytt** om du vill öppna dialogrutan.
9.    Ange "List" i fältet **Namn**.
10.    Välj **Postlista** i fältet **Artikeltyp**.
11.    Klicka på **Lägg till**.
12.    Klicka på **Nytt** om du vill öppna dialogrutan.
13.    Ange "Code" i fältet **Namn**.
14.    Välj **Sträng** i fältet **Artikeltyp**.
15.    Klicka på **Lägg till**.
16.    Klicka på **Spara**.
17.    Stäng sidan.
18.    Klicka på **Ändra status**.
19.    Klicka på **Slutför**.
20.    Klicka på **OK**.

## <a name="create-a-format-for-data-import"></a>Skapa ett format för dataimport
1.    Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.
2.    Ange "Format based on data model Model to import xml file" i fältet **Ny**.
3.    I fältet **Namn** skriver du "Format för att importera xml-fil".
4.    Välj **Ja** i fältet **Stöder dataimport**.
5.    Klicka på **Skapa konfiguration**.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>Utforma ett format för att tolka inkommande filer i XML-format
1.    Klicka på **Designer**.
2.    Klicka på **Lägg till rot** för att öppna dialogrutan.
3.    I trädet, välj **XML\Element**.
4.    Ange "root" i fältet **Namn**.
5.    Klicka på **OK**.
6.    Klicka på **Lägg till** för att öppna dialogrutan.
7.    I trädet, välj **XML\Element**.
8.    Ange "document" i fältet **Namn**.
9.    Välj **Ett många** i fältet **Sammansatt**.
10.    Klicka på **OK**.
11.    Välj **root\document** i trädet.
12.    Klicka på **Lägg till** för att öppna dialogrutan.
13.    I trädet välj **XML\Attribute**.
14.    I fältet **Namn**, ange "ID".
15.    Klicka på **OK**.
16.    Klicka på **Spara**.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Utforma en formatmappning för att spara analyserad information till datamodellen
1. Klicka på **Mappa format till modell**.
2. Klicka på **Ny**.
3. Ange eller välj ett värde i fältet **Definition**.
4. Klicka på länken på den valda raden i listan.
5. Ange "Mapping" i fältet **Namn**.
6. Klicka på **Spara**.
7. Klicka på **Designer**.
8. Expandera **format** i trädet.
9. I trädet expandera **format\root: XML Element(root)**.
10.    I trädet väljer du **format\root: XML Element(root)\document: XML Element 1..* (dokument)**.
11.    Klicka på **Bind**.
12.    I trädet expanderar du **format\root: XML Element(root)\document: XML Element 1..* (dokument)**.
13.    I trädet väljer du **format\root: XML Element(root)\document: XML Element 1..* (dokument)\id**.
14.    Expandera **List = format.root.document**.
15.    Välj **List = format.root.document\Code** i trädet.
16.    Klicka på **Bind**.
17.    Klicka på **Spara**.
18.    Stäng sidan.
 
## <a name="run-format-mapping"></a>Kör mappning av format
1. Klicka på **Kör**.
2. Klicka på **Bläddra** och välj **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
3. Klicka på **OK**.

> [!NOTE]
> Den valda filen har inte importerats eftersom formatdesignen innehåller attributet "id" för elementet "document", men den importerade filen innehåller inget sådant attribut.

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a>Ändra formatstrukturen så att XML-attributet hanteras som valfritt
1. Stäng sidan.
2. Expandera **root\document** i trädet.
3. Välj **root\document\id** i trädet.
4. Välj **ja** i fältet **tom sträng för saknat attribut**.
5. Klicka på **Spara**.
 
## <a name="run-format-mapping-to-test-changes"></a>Kör formatmappning fär att testa ändringar
1. Klicka på **Mappa format till modell**.
2. Klicka på **Kör**.
3. Klicka på **Bläddra** och välj fältet **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
4. Klicka på **OK**.
5. Granska den skapade filen. 

> [!NOTE]
> Samma fil har importerats som formatdesignen betraktar nu attributet "ID" för "dokument"-elementet som valfritt.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]