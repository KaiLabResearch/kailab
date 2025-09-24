# Dynamic Author Images

This Hugo site now supports dynamic author profile images with the following priority system:

## Image Priority Order

1. **Custom Image** (highest priority)
   - If an author has an `image` field in their front matter, it will be used
   - Example: `image: "images/authors/polla-fattah.jpg"`

2. **Gravatar** (medium priority)
   - If an author has an `email` field but no custom image, Gravatar will be used
   - Automatically generates an avatar based on the email address
   - Example: `email: "john.doe@kailab.org"`

3. **Default Avatar** (lowest priority)
   - If no custom image or email is provided, the default avatar is used
   - Default: `/images/avatar.png`

## How to Add Author Images

### Option 1: Custom Image
1. Add your image to `assets/images/authors/` directory
2. Update the author's front matter:
   ```yaml
   ---
   title: "Dr. Your Name"
   name: "Your Name"
   email: "your.email@kailab.org"
   image: "images/authors/your-image.jpg"  # Add this line
   description: "Your description"
   ---
   ```

### Option 2: Gravatar
1. Simply ensure the author has an email field:
   ```yaml
   ---
   title: "Dr. Your Name"
   name: "Your Name"
   email: "your.email@kailab.org"  # This will use Gravatar
   description: "Your description"
   ---
   ```

### Option 3: Default Avatar
1. Don't add any image or email fields - the default avatar will be used automatically

## Supported Image Formats
- JPG/JPEG
- PNG
- WebP
- Any format supported by Hugo's image processing

## Image Sizes
- **Author List Page**: 120x120 pixels
- **Author Single Page**: 200x200 pixels
- **Author Cards**: 120x120 pixels

## File Structure
```
assets/
└── images/
    ├── authors/           # Custom author images
    │   ├── polla-fattah.jpg
    │   └── your-name.jpg
    └── avatar.png         # Default avatar
```

## Templates Updated
- `themes/hugoplate/layouts/authors/single.html`
- `themes/hugoplate/layouts/authors/list.html`
- `themes/hugoplate/layouts/partials/components/author-card.html`

All templates now use the same dynamic image logic for consistency.

