# ConvertImgToPdf
from PIL import Image

def convert_image_to_pdf(image_path, output_pdf_path):
    # Open the image
    image = Image.open("flower.jpg")

    # Convert image mode if needed (JPG might be in RGB, PNG might be RGBA)
    if image.mode in ("RGBA", "P"):
        image = image.convert("RGB")

    # Save the image as a PDF
    image.save(output_pdf_path, "PDF")
    print(f"PDF saved successfully at: {output_pdf_path}")

# Example usage
if __name__ == "__main__":
    input_image = "input_image.png"  # Replace with your image file
    output_pdf = "output_file.pdf"   # Your desired PDF output name
    convert_image_to_pdf(input_image, output_pdf)
