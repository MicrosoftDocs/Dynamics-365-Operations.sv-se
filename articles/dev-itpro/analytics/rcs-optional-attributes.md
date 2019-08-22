---
title: Importera filer i XML-format med valfria attribut
description: Det här avsnittet innehåller information om hur du utformar ER-format, som anger XML-attribut för tolkning av inkommande elektroniska dokument i XML-format.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: eb5d721784f45097ab466f75d43256495aac36ca
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850005"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a>Importera filer i XML-format med valfria attribut

Du kan utforma elektronisk rapportering (ER)-format som tolkar inkommande elektroniska dokument dokument i XML-format. Vissa attribut för XML-element kan anges i designat ER-format som valfritt. Det gör att du kan hantera inkommande filer med och utan sådana XML-attribut korrekt. Du kan sedan använda innehållet från dessa filer till att uppdatera programdata.

Om du vill veta mer om den här funktionen följer du anvisningarna i avsnittet [RCS importerar filer i XML-format med valfria attribut](tasks/import-files-xml-format-optional-attributes.md) som ingår i affärsprocessen 7.5.4.3 Hämta/utveckla IT-/lösningskomponenter (10677). Du kan hämta dne här uppgiftsguiden och kopplade exempelfiler från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).


| Beskrivning av innehåll       | Fil                                                         |
|---------------------------|--------------------------------------------------------------|
| Exempelfiler iXML-format | IncomingDocumentToLearnHowToHandleOptionalAttributes.xml     |
| Uppgiften guide                | RCS Importera filer i XML-format med valfria attribut.axtr |


I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan designa ER-formatkonfiguration att importera filer i XML-format med valfria attribut. För att slutföra dessa steg måste du först slutföra stegen i proceduren [Skapa en konfigurationsleverantör och välj den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md). Innan du börjar hämtar du filen IncomingDocumentToLearnHowToHandleOptionalAttributes.xml från Microsoft Download Center och sparar den lokalt https://go.microsoft.com/fwlink/?linkid=874684.

1. Gå till **Organisationsadministration** > **Arbetsytor** > **Elektronisk rapportering**.
2. Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i avsnittet [Skapa en konfigurationsleverantör och välj den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Klicka på **Rapporteringskonfiguration**.

## <a name="create-a-new-data-model-configuration"></a>Skapa en ny datamodellskonfiguration
1. Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.
2. I fältet **Namn** skriver du "Model to import xml file".
3. Klicka på **Skapa konfiguration**.
4. Klicka på **Designer**.
5. Klicka på **Nytt** om du vill öppna dialogrutan.
6. Ange "Root" i fältet **Namn**.
7. Klicka på **Lägg till**.
8. Klicka på **Nytt** om du vill öppna dialogrutan.
9. Ange "List" i fältet **Namn**.
10. Välj **Postlista** i fältet **Artikeltyp**.
11. Klicka på **Lägg till**.
12. Klicka på **Nytt** om du vill öppna dialogrutan.
13. Ange "Code" i fältet **Namn**.
14. Välj **Sträng** i fältet **Artikeltyp**.
15. Klicka på **Lägg till**.
16. Klicka på **Spara**.
17. Stäng sidan.
18. Klicka på **Ändra status**.
19. Klicka på **Slutför**.
20. Klicka på **OK**.

## <a name="create-a-format-for-data-import"></a>Skapa ett format för dataimport
1. Klicka på **Skapa konfiguration** om du vill öppna dialogrutan.
2. Ange "Format based on data model Model to import xml file" i fältet **Ny**.
3. I fältet **Namn** skriver du "Format för att importera xml-fil". 
4. Välj **Ja** i fältet **Stöder dataimport**.
5. Klicka på **Skapa konfiguration**.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>Utforma ett format för att tolka inkommande filer i XML-format
1. Klicka på **Designer**.
2. Klicka på **Lägg till rot** för att öppna dialogrutan.
3. I trädet, välj **XML\Element**.
4. Ange "root" i fältet **Namn**.
5. Klicka på **OK**.
6. Klicka på **Lägg till** för att öppna dialogrutan.
7. I trädet, välj **XML\Element**.
8. Ange "document" i fältet **Namn**.
9. Välj **Ett många** i fältet **Sammansatt**.
10. Klicka på **OK**.
11. Välj **root\document** i trädet.
12. Klicka på **Lägg till** för att öppna dialogrutan.
13. I trädet välj **XML\Attribute**.
14. I fältet **Namn**, ange "id".
15. Klicka på **OK**.
16. Klicka på **Spara**.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Utforma en formatmappning för att spara analyserad information till datamodellen
1.  Klicka på **Mappa format till modell**.
2.  Klicka på **Ny**.
3.  Ange eller välj ett värde i fältet **Definition**.
4.  Ange "Mapping" i fältet **Namn**.
5.  Klicka på **Spara**.
6.  Klicka på **Designer**.
7.  Expandera **format** i trädet.
8.  I trädet expandera **format\root: XML Element(root)**.
9.  I trädet väljer du **format\root: XML Element(root)\document: XML Element 1..* (dokument)**.
10. Klicka på **Bind**.
11. I trädet expanderar du **format\root: XML Element(root)\document: XML Element 1..* (dokument)**.
12. I trädet väljer du **format\root: XML Element(root)\document: XML Element 1..* (dokument)\id**.
13. Expandera **List = format.root.document**.
14. Välj **List = format.root.document\Code** i trädet.
15. Klicka på **Bind**.
16. Klicka på **Spara**.
17. Stäng sidan.

## <a name="run-format-mapping"></a>Kör mappning av format
1. Klicka på **Kör**.
2. Klicka på **Bläddra** och välj filen **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
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
3. Klicka på **Bläddra** och välj filen **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
4. Klicka på **OK**.
5. Granska den skapade filen. Observera att samma fil har importerats som formatdesignen betraktar nu attributet "ID" för "dokument"-elementet som valfritt.
