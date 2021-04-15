---
title: Ange en anpassad lagringsplats för skapade dokument
description: Det här avsnittet beskriver hur du utökar listan över lagringsplatser för dokument som elektronisk rapporteringsformat (ER) genererar.
author: NickSelin
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: dab70b213efc7e7a3537aa2b47b9edf38d492d34
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753730"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a>Ange en anpassad lagringsplats för skapade dokument

[!include[banner](../includes/banner.md)]

API (application programming interface) för ramverket för elektronisk rapportering (ER) låter dig utöka lagringsplatser för dokument som ER-format genererar. Det här avsnittet innehåller en översikt över de viktigaste åtgärderna som du måste utföra om du vill lägga till en egen lagringsplats.

## <a name="prerequisites"></a>Förutsättningar

Du måste distribuera en topologi som stöder kontinuerlig version. (Mer information finns i [distribuera topologier som stöder kontinuerlig version och testa automatisering](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) Du måste ha tillgång till den här topologin för en av följande roller:

- Utvecklare för elektronisk rapportering
- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

Du måste också ha tillgång till utvecklingsmiljön för den här topologin.

## <a name="create-or-import-an-er-format-configuration"></a>Skapa eller importera en ER-formatkonfiguration

I den aktuella topologin [skapa ett nytt ER-format](tasks/er-format-configuration-2016-11.md) för att skapa dokument som du vill lägga till en egen lagringsplats för. Alternativt kan du [importera ett befintligt ER-format till den här topologin](general-electronic-reporting-manage-configuration-lifecycle.md).

![Formatdesignersida](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> ER-formatet du skapar eller importerar måste innehålla minst ett av följande formatelement:
>
> - Fil
> - Mapp
> - Sammanfoga
> - Bilaga

## <a name="create-a-new-document-type"></a>Skapa en ny dokumenttyp

Om du vill ange hur dokument som ett ER-format genereras skickas, måste du konfigurera [Elektronisk rapportering (ER)-destinationer](electronic-reporting-destinations.md). I varje ER-destination som konfigureras för att lagra genererade dokument som filer måste du ange en dokumenttyp för ramverket för dokumenthantering. Olika typer av dokumenttyper kan användas för att skicka dokument som ger upphov till olika ER-format.

1. Lägg till en ny [dokumenttyp](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management) för ER-formatet som du har skapat eller tidigare importerat. I bilden nedan är dokumenttypen **FileX**.
2. Inkludera ett specifikt nyckelord i dess namn för att skilja den här dokumenttypen från andra typer av dokument. I bilden nedan är namnet exempelvis **(LOKAL) mapp**.
3. I fältet **klass** anger du **bifoga fil**.
4. I fältet **grupp** anger du **fil**.

![Sida för dokumenttyper](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> Dokumenttyper är företagsspecifika. Om du vill använda ett ER-format med en konfigurerad destination i flera företag, måste du konfigurera en separat dokumenttyp i varje företag.

## <a name="review-source-code"></a>Granska källkod

Granska koden för metoden **insertFile()** för klassen **ERDocuManagement**. Observera att händelsen **AttachingFile()** utlöses medan den genererade filen bifogas till en post.


```xpp
/// <summary>
/// Inserts file as attachment in Document Management.
/// </summary>
/// <param name = "_owner">A record as the attachment owner.</param>
/// <param name = "_stream">The file stream.</param>
/// <param name = "_filePath">The file path with name.</param>
/// <param name = "_attachmentName">The name of file attachment.</param>
/// <returns>The reference to inserted file.</returns>
[Hookable(false)]
public DocuRef insertFile(
    Common _owner, 
    System.IO.Stream _stream, 
    str _filePath, 
    str _attachmentName, 
    DocuTypeId _docuTypeId)
{
    DocuRef docuRef;
    if (_stream)
    {
        DocuType::createDefaults();
        if (!this.isDocuTypeValid(_docuTypeId))
        {
            throw error(strFmt("@ElectronicReporting:DocuTypeIsNotValid", _docuTypeId));
        }
        var args = ERDocuManagementAttachingFileEventArgs::construct(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        ERDocuManagementEvents::onAttachingFile(args);
        if (args.isHandled())
        {
            docuRef = args.getDocuRef();
        }
        else
        {
            docuRef = this.attachFile(_owner, _stream, _filePath, _attachmentName, _docuTypeId);
        }
    }
    return docuRef;
}
```

Händelsen **AttachingFile()** utlöses när följande ER-destinationer bearbetas:

- **Arkivera** – när denna destination används skapas en ny post för ER-formatet i tabellen ERFormatMappingRunJobTable. Fältet **arkiverade** i den här posten har tilldelats **falsk**. Om ER-formatet körs korrekt, kommer det genererade dokumentet kopplas till denna post och händelsen **AttachingFile()** utlöses. Dokumenttypen som väljs i ER-destinationen bestämmer lagringsplats för den bifogade filen (Microsoft Azure lagring eller en Microsoft SharePoint-mapp).
- **Jobbarkiv** – när denna destination används skapas en ny post för ER-formatet i tabellen ERFormatMappingRunJobTable. Fältet **arkiverade** i den här posten har tilldelats **sant**. Om ER-formatet körs korrekt, kommer det genererade dokumentet kopplas till denna post och händelsen **AttachingFile()** utlöses. Dokumenttypen som konfigureras i ER-parametrarna bestämmer lagringsplats för den bifogade filen (Azure lagring eller en SharePoint-mapp).

![Sida för parametrar för elektronisk rapportering](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a>Konfigurera ER-destination

1. Konfigurera arkiverade destinationen för en av de ovan nämnda elementfilerna (fil, mapp, sammanslagning eller bilaga) för ER-formatet som du skapat eller importerat. Instruktioner finns i [ER konfigurera destinationer](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).
2. Använd den dokumenttyp som du lagt till tidigare konfigurerade destinationen. (I exemplet i det här avsnittet är dokumenttypen **FileX**.)

![Dialogruta för destinationsinställningar](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a>Modifiera källkod

1. Lägg till en ny klass i Microsoft Visual Studio projekt och skriv kod för att prenumerera på händelsen **AttachingFile()** som nämnts tidigare. (Mer information om utbyggbarhetsmönstret som används finns i [Svara genom att använda EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) Skriv till exempel kod i den nya klassen som utför följande åtgärder:

    1. Lagra genererade filer i en mapp i det lokala filsystemet på servern som kör tjänsten Application Object Server (AOS).
    2. Lagra endast dessa genererade filer när nya dokumenttypen (till exempel typen **FileX** som har nyckelordet ”(LOKAL)” i namnet) används när en fil som är kopplad till posten i loggen ER-körningens jobblogg.

    ```xpp
    class ERDocuSubscriptionSample
    {
        void new()
        {
        }
        [SubscribesTo(classStr(ERDocuManagementEvents), 
        staticDelegateStr(ERDocuManagementEvents, 
        attachingFile))]
        public static void ERDocuManagementEvents_attachingFile(ERDocuManagementAttachingFileEventArgs _args)
        {
            if (!_args.isHandled())
            {
                DocuType docuType = DocuType::find(_args.getDocuTypeId());
                if (strContains(docuType.Name, '(LOCAL)'))
                {
                    _args.markAsHandled();
                    var stream = _args.getStream();
                    if (stream.CanSeek)
                    {
                        stream.Seek(0, System.IO.SeekOrigin::Begin);
                    }
                    using (var localStream = System.IO.File::OpenWrite(@'c:\0\' + _args.getAttachmentName()))
                    {
                        stream.CopyTo(localStream);
                    }
                }
            }
        }
    }
    ```

2. Återskapa ditt projekt

## <a name="run-the-er-format-that-you-created-or-imported"></a>Kör ER-formatet som du har skapat eller importerat

1. Kör ER-formatet som du har skapat eller importerat.
2. Gå till **Organisationsadministration \> Elektronisk rapportering \> Elektroniska rapporteringsjobb**. Hitta den post som har skapats för detta körningsjobbet och som har den genererade filen bifogad till den.
3. Utforska den lokala **C:\\0**-mapp för att hitta samma genererade fil.

## <a name="additional-resources"></a>Ytterligare resurser

- [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)
- [Startsida för utbyggbarhet](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]