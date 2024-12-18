# Ex.08 Design of Interactive Image Gallery
## Date:18/12/2024

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gallery</title>
    <style>
        body {
            margin: 0;
            background: #383837;
            padding: 20px;
        }

        .gallery {
    display: flex;
    flex-wrap: wrap;
    justify-content: center; /* Centers the images horizontally */
    align-items: center; /* Centers the content vertically (if applicable) */
    gap: 20px; /* Add space between the images */
    margin: 0 auto; /* Ensures the container itself is centered */
    max-width: 1400px;
    padding: 20px;
}


.gallery-item {
    flex: 0 1 calc(20% - 20px); /* Each item takes roughly 20% of the container width */
    max-width: 250px; /* Limits maximum width */
    position: relative;
    border-radius: 8px;
    overflow: hidden;
    cursor: pointer;
    background: white;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    aspect-ratio: 3 / 4; /* Ensures uniform size */
}

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .gallery-item img {
            width: 100%;
            height: auto;
            display: block;
            transition: transform 0.3s;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .image-caption {
            position: absolute;
            bottom: 0;
            width: 100%;
            padding: 15px;
            background: linear-gradient(transparent, rgba(0,0,0,0.7));
            color: white;
            transform: translateY(100%);
            transition: transform 0.3s;
            text-align: center;
        }

        .gallery-item:hover .image-caption {
            transform: translateY(0);
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.9);
            padding: 20px;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }

        .modal img {
            max-width: 90%;
            max-height: 90vh;
            object-fit: contain;
        }

        .close-button {
            position: absolute;
            top: 20px;
            right: 30px;
            color: white;
            font-size: 30px;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .gallery {
                columns: 2;
            }
        }

        @media (max-width: 480px) {
            .gallery {
                columns: 1;
            }
        }
    </style>
</head>
<body>
    <div class="gallery">
        <!-- Using different dimensions for each image -->
        <div class="gallery-item">
            <img src="/images/1.jpeg" alt="Tall Portrait">
            <div class="image-caption">Mountain View</div>
        </div>
        <div class="gallery-item">
            <img src="/images/3.jpg" alt="Landscape">
            <div class="image-caption">Ocean Vista</div>
        </div>
        <div class="gallery-item">
            <img src="/images/2.jpeg" alt="Portrait">
            <div class="image-caption">Forest Path</div>
        </div>
        <div class="gallery-item">
            <img src="/images/5.jpeg" alt="Square">
            <div class="image-caption">Desert Sunset</div>
        </div>
        <div class="gallery-item">
            <img src="/images/4.jpeg" alt="Extra Tall">
            <div class="image-caption">City Lights</div>
        </div>
        
    </div>

    <div class="modal">
        <span class="close-button">&times;</span>
        <img src="" alt="Modal Image">
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const modal = document.querySelector('.modal');
            const modalImg = modal.querySelector('img');

            document.querySelector('.gallery').addEventListener('click', e => {
                const item = e.target.closest('.gallery-item');
                if (item) {
                    modal.style.display = 'flex';
                    modalImg.src = item.querySelector('img').src;
                }
            });

            modal.addEventListener('click', e => {
                if (e.target !== modalImg) modal.style.display = 'none';
            });

            document.addEventListener('keydown', e => {
                if (e.key === 'Escape') modal.style.display = 'none';
            });
        });
    </script>
</body>
</html>

```
## OUTPUT:

![image](https://github.com/user-attachments/assets/3bdbc216-99df-45fe-95a5-055473c56364)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
