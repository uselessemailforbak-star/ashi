# How to Replace the Placeholder Photo

The website currently uses a placeholder image from Unsplash. To use your own photo:

## Quick Steps:

1. **Add your photo** - Copy your JPG/PNG file to the project folder (e.g., `my-photo.jpg`)

2. **Update the HTML** - In [index.html](index.html), find line ~153 and change:
   ```html
   <img src="https://images.unsplash.com/photo-1535712066554-a87d19ea0dfd?w=400&h=400&fit=crop" alt="Sorry" class="profile-img">
   ```
   to:
   ```html
   <img src="my-photo.jpg" alt="Sorry" class="profile-img">
   ```

3. **Done!** - Your photo will now display in the circular frame

## Best Photo Format:
- **Size:** 400x400px or larger
- **Format:** JPG, PNG, or WebP
- **File size:** Under 500KB for fast loading
- **Shape:** Square images work best (the CSS makes it circular)

## If You Don't Have a Photo Yet:

You can use any of these free placeholder services:
- **Unsplash** (current): https://unsplash.com - free high-quality photos
- **Pexels**: https://pexels.com - free stock photos
- **Pixabay**: https://pixabay.com - free images
- **Your own photo**: Upload a JPG or PNG

Just replace the URL in the `src` attribute with your photo URL.

---

**Current Setup:** Uses Unsplash placeholder (free, no signup needed)
