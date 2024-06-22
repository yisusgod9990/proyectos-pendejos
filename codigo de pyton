import os
from PIL import Image
import json

def resize_and_convert_to_png(image_path, output_path):
    with Image.open(image_path) as img:
        img = img.resize((512, 512), Image.LANCZOS)  # Cambiado a Image.LANCZOS
        img = img.convert("RGBA")
        img.save(output_path, format="PNG")

def create_sticker_pack(images_folder, output_folder, pack_name, author):
    if not os.path.exists(output_folder):
        os.makedirs(output_folder)
    
    metadata = {
        "stickerPackName": pack_name,
        "stickerPackAuthor": author,
        "stickerImages": []
    }
    
    for image_file in os.listdir(images_folder):
        if image_file.lower().endswith(('png', 'jpg', 'jpeg')):
            input_path = os.path.join(images_folder, image_file)
            output_path = os.path.join(output_folder, os.path.splitext(image_file)[0] + ".png")
            resize_and_convert_to_png(input_path, output_path)
            metadata["stickerImages"].append(os.path.basename(output_path))
    
    metadata_path = os.path.join(output_folder, "metadata.json")
    with open(metadata_path, 'w') as metadata_file:
        json.dump(metadata, metadata_file, indent=4)
    
    print(f"Sticker pack created at {output_folder}")

if __name__ == "__main__":
    images_folder = r"C:\Users\familia bolaño\Downloads\Documents\Pictures\stickers"  # no seas pndjo cambia la ruta 
    output_folder = r"C:\Users\familia bolaño\Downloads\Documents\Pictures\stickers creados"  #no seas pndjo Cambia esta ruta
    pack_name = "Nombre de tu paquete de stickers"  #no seas pndjo Cambia esto
    author = "Autor del paquete"  # no seas pndjo Cambia esto
    
    create_sticker_pack(images_folder, output_folder, pack_name, author)
   
   #primero y obligatoriamente para que el codigo te funcione necesitas instalar el pip ese es el comando que colocaras en la terminal de python  "pip install Pillow" y por nada este codigo esta hecho por jesus guzman suscribete a mi canal  en mi youtube"https://www.youtube.com/channel/UC5o6TqX3GhmoYMUU5kSnpwQ"
