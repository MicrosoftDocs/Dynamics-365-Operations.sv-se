---
title: Ange en anpassad lagringsplats för skapade dokument
description: Det här avsnittet beskriver hur du utökar listan över lagringsplatser för dokument som elektronisk rapporteringsformat (ER) genererar.
author: NickSelin
manager: AnnBe
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: a1c41cd4440eaf70f720bfd64884e6ef4662f87a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181483"
---
# <a name="specify-a-custom-storage-location-for-generated-documents"></a><span data-ttu-id="80083-103">Ange en anpassad lagringsplats för skapade dokument</span><span class="sxs-lookup"><span data-stu-id="80083-103">Specify a custom storage location for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="80083-104">API (application programming interface) för ramverket för elektronisk rapportering (ER) låter dig utöka lagringsplatser för dokument som ER-format genererar.</span><span class="sxs-lookup"><span data-stu-id="80083-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="80083-105">Det här avsnittet innehåller en översikt över de viktigaste åtgärderna som du måste utföra om du vill lägga till en egen lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="80083-105">This topic includes an overview of the main tasks that you must complete to add a custom storage location.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80083-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="80083-106">Prerequisites</span></span>

<span data-ttu-id="80083-107">Du måste distribuera en topologi som stöder kontinuerlig version.</span><span class="sxs-lookup"><span data-stu-id="80083-107">You must deploy a topology that supports continuous build.</span></span> <span data-ttu-id="80083-108">(Mer information finns i [distribuera topologier som stöder kontinuerlig version och testa automatisering](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) Du måste ha tillgång till den här topologin för en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="80083-108">(For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).) You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="80083-109">Utvecklare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="80083-109">Electronic reporting developer</span></span>
- <span data-ttu-id="80083-110">Konsult för funktionen för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="80083-110">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="80083-111">Systemadministratör</span><span class="sxs-lookup"><span data-stu-id="80083-111">System administrator</span></span>

<span data-ttu-id="80083-112">Du måste också ha tillgång till utvecklingsmiljön för den här topologin.</span><span class="sxs-lookup"><span data-stu-id="80083-112">You must also have access to the development environment for this topology.</span></span>

## <a name="create-or-import-an-er-format-configuration"></a><span data-ttu-id="80083-113">Skapa eller importera en ER-formatkonfiguration</span><span class="sxs-lookup"><span data-stu-id="80083-113">Create or import an ER format configuration</span></span>

<span data-ttu-id="80083-114">I den aktuella topologin [skapa ett nytt ER-format](tasks/er-format-configuration-2016-11.md) för att skapa dokument som du vill lägga till en egen lagringsplats för.</span><span class="sxs-lookup"><span data-stu-id="80083-114">In the current topology, [create a new ER format](tasks/er-format-configuration-2016-11.md) to generate documents that you plan to add a custom storage location for.</span></span> <span data-ttu-id="80083-115">Alternativt kan du [importera ett befintligt ER-format till den här topologin](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="80083-115">Alternatively, [import an existing ER format into this topology](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![Formatdesignersida](media/er-extend-file-storages-format.png)

> [!IMPORTANT]
> <span data-ttu-id="80083-117">ER-formatet du skapar eller importerar måste innehålla minst ett av följande formatelement:</span><span class="sxs-lookup"><span data-stu-id="80083-117">The ER format that you create or import must contain at least one of the following format elements:</span></span>
>
> - <span data-ttu-id="80083-118">Fil</span><span class="sxs-lookup"><span data-stu-id="80083-118">File</span></span>
> - <span data-ttu-id="80083-119">Mapp</span><span class="sxs-lookup"><span data-stu-id="80083-119">Folder</span></span>
> - <span data-ttu-id="80083-120">Sammanfoga</span><span class="sxs-lookup"><span data-stu-id="80083-120">Merger</span></span>
> - <span data-ttu-id="80083-121">Bilaga</span><span class="sxs-lookup"><span data-stu-id="80083-121">Attachment</span></span>

## <a name="create-a-new-document-type"></a><span data-ttu-id="80083-122">Skapa en ny dokumenttyp</span><span class="sxs-lookup"><span data-stu-id="80083-122">Create a new document type</span></span>

<span data-ttu-id="80083-123">Om du vill ange hur dokument som ett ER-format genereras skickas, måste du konfigurera [ER-destinationer](electronic-reporting-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="80083-123">To specify how documents that an ER format generates are routed, you must configure [ER destinations](electronic-reporting-destinations.md).</span></span> <span data-ttu-id="80083-124">I varje ER-destination som konfigureras för att lagra genererade dokument som filer måste du ange en dokumenttyp för ramverket för dokumenthantering.</span><span class="sxs-lookup"><span data-stu-id="80083-124">In each ER destination that is configured to store generated documents as files, you must specify a document type of the Document management framework.</span></span> <span data-ttu-id="80083-125">Olika typer av dokumenttyper kan användas för att skicka dokument som ger upphov till olika ER-format.</span><span class="sxs-lookup"><span data-stu-id="80083-125">Different document types can be used to route documents that different ER formats generate.</span></span>

1. <span data-ttu-id="80083-126">Lägg till en ny [dokumenttyp](../../fin-and-ops/organization-administration/configure-document-management.md) för ER-formatet som du har skapat eller tidigare importerat.</span><span class="sxs-lookup"><span data-stu-id="80083-126">Add a new [document type](../../fin-and-ops/organization-administration/configure-document-management.md) for the ER format that you created or imported earlier.</span></span> <span data-ttu-id="80083-127">I bilden nedan är dokumenttypen **FileX**.</span><span class="sxs-lookup"><span data-stu-id="80083-127">In the illustration that follows, the document type is **FileX**.</span></span>
2. <span data-ttu-id="80083-128">Inkludera ett specifikt nyckelord i dess namn för att skilja den här dokumenttypen från andra typer av dokument.</span><span class="sxs-lookup"><span data-stu-id="80083-128">To differentiate this document type from other document types, include a specific keyword in its name.</span></span> <span data-ttu-id="80083-129">I bilden nedan är namnet exempelvis **(LOKAL) mapp**.</span><span class="sxs-lookup"><span data-stu-id="80083-129">For example, in the illustration that follows, the name is **(LOCAL) folder**.</span></span>
3. <span data-ttu-id="80083-130">I fältet **klass** anger du **bifoga fil**.</span><span class="sxs-lookup"><span data-stu-id="80083-130">In the **Class** field, specify **Attach file**.</span></span>
4. <span data-ttu-id="80083-131">I fältet **grupp** anger du **fil**.</span><span class="sxs-lookup"><span data-stu-id="80083-131">In the **Group** field, specify **File**.</span></span>

![Sida för dokumenttyper](media/er-extend-file-storages-document-type.png)

> [!NOTE]
> <span data-ttu-id="80083-133">Dokumenttyper är företagsspecifika.</span><span class="sxs-lookup"><span data-stu-id="80083-133">Document types are company-specific.</span></span> <span data-ttu-id="80083-134">Om du vill använda ett ER-format med en konfigurerad destination i flera företag, måste du konfigurera en separat dokumenttyp i varje företag.</span><span class="sxs-lookup"><span data-stu-id="80083-134">To use an ER format with a configured destination in multiple companies, you must configure a separate document type in each company.</span></span>

## <a name="review-source-code"></a><span data-ttu-id="80083-135">Granska källkod</span><span class="sxs-lookup"><span data-stu-id="80083-135">Review source code</span></span>

<span data-ttu-id="80083-136">Granska koden för metoden **insertFile()** för klassen **ERDocuManagement**.</span><span class="sxs-lookup"><span data-stu-id="80083-136">Review the code of the **insertFile()** method of the **ERDocuManagement** class.</span></span> <span data-ttu-id="80083-137">Observera att händelsen **AttachingFile()** utlöses medan den genererade filen bifogas till en post.</span><span class="sxs-lookup"><span data-stu-id="80083-137">Notice that the **AttachingFile()** event is raised while the generated file is attached to a record.</span></span>

```
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

<span data-ttu-id="80083-138">Händelsen **AttachingFile()** utlöses när följande ER-destinationer bearbetas:</span><span class="sxs-lookup"><span data-stu-id="80083-138">The **AttachingFile()** event is raised when the following ER destinations are processed:</span></span>

- <span data-ttu-id="80083-139">**Arkivera** – när denna destination används skapas en ny post för ER-formatet i tabellen ERFormatMappingRunJobTable.</span><span class="sxs-lookup"><span data-stu-id="80083-139">**Archive** – When this destination is used, a new record for the ER format that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="80083-140">Fältet **arkiverade** i den här posten har tilldelats **falsk**.</span><span class="sxs-lookup"><span data-stu-id="80083-140">The **Archived** field in this record is set to **False**.</span></span> <span data-ttu-id="80083-141">Om ER-formatet körs korrekt, kommer det genererade dokumentet kopplas till denna post och händelsen **AttachingFile()** utlöses.</span><span class="sxs-lookup"><span data-stu-id="80083-141">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="80083-142">Dokumenttypen som väljs i ER-destinationen bestämmer lagringsplats för den bifogade filen (Microsoft Azure lagring eller en Microsoft SharePoint-mapp).</span><span class="sxs-lookup"><span data-stu-id="80083-142">The document type that is selected in this ER destination determines the storage location for the attached file (Microsoft Azure Storage or a Microsoft SharePoint folder).</span></span>
- <span data-ttu-id="80083-143">**Jobbarkiv** – när denna destination används skapas en ny post för ER-formatet i tabellen ERFormatMappingRunJobTable.</span><span class="sxs-lookup"><span data-stu-id="80083-143">**Job archive** – When this destination is used, a new record for the ER form that is run is created in the ERFormatMappingRunJobTable table.</span></span> <span data-ttu-id="80083-144">Fältet **arkiverade** i den här posten har tilldelats **sant**.</span><span class="sxs-lookup"><span data-stu-id="80083-144">The **Archived** field in this record is set to **True**.</span></span> <span data-ttu-id="80083-145">Om ER-formatet körs korrekt, kommer det genererade dokumentet kopplas till denna post och händelsen **AttachingFile()** utlöses.</span><span class="sxs-lookup"><span data-stu-id="80083-145">If the ER format is successfully run, the generated document is attached to this record, and the **AttachingFile()** event is raised.</span></span> <span data-ttu-id="80083-146">Dokumenttypen som konfigureras i ER-parametrarna bestämmer lagringsplats för den bifogade filen (Azure lagring eller en SharePoint-mapp).</span><span class="sxs-lookup"><span data-stu-id="80083-146">The document type that is configured in the ER parameters determines the storage location for the attached file (Azure Storage or a SharePoint folder).</span></span>

![Sida för parametrar för elektronisk rapportering](media/er-extend-file-storages-parameters.png)

## <a name="configure-an-er-destination"></a><span data-ttu-id="80083-148">Konfigurera ER-destination</span><span class="sxs-lookup"><span data-stu-id="80083-148">Configure an ER destination</span></span>

1. <span data-ttu-id="80083-149">Konfigurera arkiverade destinationen för en av de ovan nämnda elementfilerna (fil, mapp, sammanslagning eller bilaga) för ER-formatet som du skapat eller importerat.</span><span class="sxs-lookup"><span data-stu-id="80083-149">Configure the archived destination for one of the previously mentioned elements (file, folder, merger, or attachment) of the ER format that you created or imported.</span></span> <span data-ttu-id="80083-150">Instruktioner finns i [ER konfigurera destinationer](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span><span class="sxs-lookup"><span data-stu-id="80083-150">For guidance, see [ER Configure destinations](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-destinations-2016-11).</span></span>
2. <span data-ttu-id="80083-151">Använd den dokumenttyp som du lagt till tidigare konfigurerade destinationen.</span><span class="sxs-lookup"><span data-stu-id="80083-151">Use the document type that you added earlier for the configured destination.</span></span> <span data-ttu-id="80083-152">(I exemplet i det här avsnittet är dokumenttypen **FileX**.)</span><span class="sxs-lookup"><span data-stu-id="80083-152">(For the example in this topic, the document type is **FileX**.)</span></span>

![Dialogruta för destinationsinställningar](media/er-extend-file-storages-destination.png)

## <a name="modify-source-code"></a><span data-ttu-id="80083-154">Modifiera källkod</span><span class="sxs-lookup"><span data-stu-id="80083-154">Modify source code</span></span>

1. <span data-ttu-id="80083-155">Lägg till en ny klass i Microsoft Visual Studio projekt och skriv kod för att prenumerera på händelsen **AttachingFile()** som nämnts tidigare.</span><span class="sxs-lookup"><span data-stu-id="80083-155">Add a new class to your Microsoft Visual Studio project, and write code to subscribe to the **AttachingFile()** event that was mentioned earlier.</span></span> <span data-ttu-id="80083-156">(Mer information om utbyggbarhetsmönstret som används finns i [Svara genom att använda EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) Skriv till exempel kod i den nya klassen som utför följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="80083-156">(For more information about the extensibility pattern that is used, see [Respond by using EventHandlerResult](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/extensibility/respond-event-handler-result).) For example, in the new class, write code that performs the following actions:</span></span>

    1. <span data-ttu-id="80083-157">Lagra genererade filer i en mapp i det lokala filsystemet på servern som kör tjänsten Application Object Server (AOS).</span><span class="sxs-lookup"><span data-stu-id="80083-157">Store generated files in a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    2. <span data-ttu-id="80083-158">Lagra endast dessa genererade filer när nya dokumenttypen (till exempel typen **FileX** som har nyckelordet ”(LOKAL)” i namnet) används när en fil som är kopplad till posten i loggen ER-körningens jobblogg.</span><span class="sxs-lookup"><span data-stu-id="80083-158">Store these generated files only when the new document type (for example, the **FileX** type that has the "(LOCAL)" keyword in its name) is used while a file is attached to the record in the ER execution job log.</span></span>

    ```
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

2. <span data-ttu-id="80083-159">Återskapa ditt projekt</span><span class="sxs-lookup"><span data-stu-id="80083-159">Rebuild your project.</span></span>

## <a name="run-the-er-format-that-you-created-or-imported"></a><span data-ttu-id="80083-160">Kör ER-formatet som du har skapat eller importerat</span><span class="sxs-lookup"><span data-stu-id="80083-160">Run the ER format that you created or imported</span></span>

1. <span data-ttu-id="80083-161">Kör ER-formatet som du har skapat eller importerat.</span><span class="sxs-lookup"><span data-stu-id="80083-161">Execute the ER format that you created or imported.</span></span>
2. <span data-ttu-id="80083-162">Gå till **Organisationsadministration \> Elektronisk rapportering \> Elektroniska rapporteringsjobb**.</span><span class="sxs-lookup"><span data-stu-id="80083-162">Go to **Organization administration \> Electronic reporting \> Electronic reporting jobs**.</span></span> <span data-ttu-id="80083-163">Hitta den post som har skapats för detta körningsjobbet och som har den genererade filen bifogad till den.</span><span class="sxs-lookup"><span data-stu-id="80083-163">Find the record that was created for this execution job, and that has the generated file attached to it.</span></span>
3. <span data-ttu-id="80083-164">Utforska den lokala **C:\\0**-mapp för att hitta samma genererade fil.</span><span class="sxs-lookup"><span data-stu-id="80083-164">Explore the local **C:\\0** folder to find same generated file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="80083-165">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="80083-165">Additional resources</span></span>

- [<span data-ttu-id="80083-166">Destinationer för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="80083-166">Electronic reporting destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="80083-167">Startsida för utbyggbarhet</span><span class="sxs-lookup"><span data-stu-id="80083-167">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)
