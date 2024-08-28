var folderID = "1Ft_a8gdKQYbjpwux6iZugRkVj7rXKPt_"; //Replace the "root"with folder ID to upload files to a specific folder

function doGet() {
  return HtmlService.createTemplateFromFile('form').evaluate();
}

function include(filename) {
  return HtmlService.createHtmlOutputFromFile(filename)
      .getContent();
}

function uploadFiles(formObject) {
  try {
    var folder = DriveApp.getFolderById(folderID);
    
    // Check if file exists in formObject and is not null
    if (formObject.myFile && formObject.myFile.length > 0) {
      var blob = formObject.myFile;
      var file = folder.createFile(blob);
      file.setDescription("Uploaded by " + formObject.first_name);
      fileUrl = file.getUrl();
      fileName = file.getName();
    } else {
      fileUrl = "Record saved without a file";
    }

    return fileUrl; // Return the file URL
  } catch (error) {
    return error.toString();
  }
}
