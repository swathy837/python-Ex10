import os
from zipfile import ZipFile, ZIP_DEFLATED

def zip_folder(folder_path, output_zip):
    with ZipFile(output_zip, 'w', ZIP_DEFLATED) as zipf:
        for root, dirs, files in os.walk(folder_path):
            for file in files:
                file_path = os.path.join(root, file)
                arcname = os.path.relpath(file_path, os.path.join(folder_path, '..'))
                zipf.write(file_path, arcname)
    print(f"Successfully created: {output_zip}")


def unzip_folder(zip_path, extract_to):
    with ZipFile(zip_path, 'r') as zip_ref:
        # extractall restores all files and subfolders
        zip_ref.extractall(extract_to)
        print(f"Extracted to: {extract_to}")

        # Displaying file names from the zip using namelist()
        print("Files in archive:")
        for name in zip_ref.namelist():
            print(f" - {name}")

folder_to_zip = "my_documents"
zip_name = "archive.zip"
restore_location = "restored_files"


if not os.path.exists(folder_to_zip):
    os.makedirs(folder_to_zip)
    with open(f"{folder_to_zip}/note1.txt", "w") as f: f.write("Hello World")
    with open(f"{folder_to_zip}/note2.txt", "w") as f: f.write("Python Zipping")
zip_folder(folder_to_zip, zip_name)
unzip_folder(zip_name, restore_location)
