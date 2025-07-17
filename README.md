# City of Miami Financial Information Portal

A modern, responsive web application providing access to the City of Miami's key financial documents and reports. Built with HTML, Tailwind CSS, and Alpine.js for a seamless user experience.

## Features

- **Responsive Design**: Optimized for desktop, tablet, and mobile devices
- **Dark Mode Toggle**: User-friendly dark/light theme switching
- **Tabbed Navigation**: Organized content sections for easy browsing
- **Accordion Menus**: Collapsible sections for better content organization
- **PDF Document Access**: Direct links to financial reports and documents
- **Modern UI/UX**: Clean, professional interface using Tailwind CSS

## Available Content

### Policies and Procedures
- Debt Management Policy
- Investment Policy

### EORT Actuarial Valuation Reports
- Annual reports from 2013-2024

### Cost Allocation Plans
- Fiscal year plans from 2015-2025

### Monthly Financial Reports
- Monthly reports organized by year (2016-2025)
- Collapsible accordion interface for easy navigation

### Annual Reports
- **CAFR (Comprehensive Annual Financial Reports)**: 2003-2024
- **PAFR (Popular Annual Financial Reports)**: 2004-2024
- **Single Audit Reports**: 2003-2024
- **Management Letters**: 2006-2024
- **Supplemental Reports to Bond Holders**: 2003-2024

### Debt Management
- **Summary of Outstanding Debt**: 2003-2023
- **Debt Ratios**: 2003-2023

## Technology Stack

- **HTML5**: Semantic markup structure
- **Tailwind CSS**: Utility-first CSS framework for styling
- **Alpine.js**: Lightweight JavaScript framework for interactivity
- **Google Fonts**: Inter and Merriweather for typography

## Getting Started

1. **Clone the repository**:
   ```bash
   git clone https://github.com/edgarvelr/financeprototype.git
   cd financeprototype
   ```

2. **Open the application**:
   - Simply open `index.html` in your web browser
   - No build process or server setup required

3. **Development**:
   - Edit `index.html` to modify content or styling
   - The application uses CDN links for all dependencies

## Browser Support

- Chrome
- Firefox
- Safari
- Edge
- Mobile browsers (iOS Safari, Chrome Mobile)

## Content Management Guide

### Adding New Tabs

To add a new tab to the navigation:

1. **Add Tab Button** - Locate the tab navigation section (around line 320) and add a new button:
   ```html
   <!-- New Tab Name Tab -->
   <button @click="activeTab = 'new-tab-id'" 
           :class="{'border-blue-600 text-blue-700': activeTab === 'new-tab-id', 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300': activeTab !== 'new-tab-id'}" 
           class="whitespace-nowrap py-4 px-1 border-b-2 font-medium text-sm sm:text-base transition-colors">
       New Tab Name
   </button>
   ```

2. **Add Tab Content** - Add the corresponding content section after the existing tabs:
   ```html
   <!-- ========================================
        NEW TAB NAME TAB
        ======================================== -->
   
   <!-- New tab content with smooth transitions and Alpine.js visibility control -->
   <div x-show="activeTab === 'new-tab-id'" 
        x-cloak 
        x-transition:enter="transition ease-out duration-300" 
        x-transition:enter-start="opacity-0 transform scale-95" 
        x-transition:enter-end="opacity-100 transform scale-100" 
        x-transition:leave="transition ease-in duration-200" 
        x-transition:leave-start="opacity-100 transform scale-100" 
        x-transition:leave-end="opacity-0 transform scale-95">
       <h2 class="text-3xl font-bold text-gray-800 mb-6">New Tab Name</h2>
       <ul class="space-y-3">
           <!-- Add your document links here -->
       </ul>
   </div>
   ```

### Removing Tabs

To remove a tab:

1. **Remove Tab Button** - Delete the corresponding button from the tab navigation
2. **Remove Tab Content** - Delete the entire tab content section
3. **Update Default Tab** - If removing the default tab ('policies'), update the `activeTab` initialization in the main content area

### Adding Content to Existing Tabs

#### Simple List Items
For tabs with simple document lists (like Policies, EORT, Cost Allocation):

```html
<li><a href="https://path/to/document.pdf" target="_blank" class="list-item-link">
    <strong>Document Title</strong>
    <span class="text-blue-600 font-semibold">View PDF</span>
</a></li>
```

#### Accordion Content
For tabs with accordion sections (like Monthly Reports, Annual Reports, Debt Management):

1. **Add New Accordion Section**:
   ```html
   <!-- New Accordion Section -->
   <div x-data="{ open: false }">
       <button @click="open = !open" class="w-full flex justify-between items-center p-4 bg-gray-100 hover:bg-gray-200 rounded-lg font-bold text-left transition text-lg">
           <span>Accordion Title</span>
           <span x-text="open ? '−' : '+'" class="text-2xl font-mono"></span>
       </button>
       <div x-show="open" 
            x-transition:enter="transition ease-out duration-300" 
            x-transition:enter-start="opacity-0 transform scale-95" 
            x-transition:enter-end="opacity-100 transform scale-100" 
            x-transition:leave="transition ease-in duration-200" 
            x-transition:leave-start="opacity-100 transform scale-100" 
            x-transition:leave-end="opacity-0 transform scale-95" 
            class="p-4 bg-white border rounded-b-lg">
           <ul class="space-y-3">
               <!-- Add your document links here -->
           </ul>
       </div>
   </div>
   ```

2. **Add Documents to Accordion**:
   ```html
   <li><a href="https://path/to/document.pdf" target="_blank" class="list-item-link">
       <strong>Document Title</strong>
       <span class="text-blue-600 font-semibold">View PDF</span>
   </a></li>
   ```

### Removing Content

#### Remove Individual Documents
Simply delete the corresponding `<li>` element containing the document link.

#### Remove Accordion Sections
Delete the entire accordion `<div>` section, including:
- The button element
- The content div with all its Alpine.js attributes
- All document links within that accordion

### Content Organization Best Practices

#### Document Naming Convention
- Use consistent naming: "Document Type - Year" (e.g., "Monthly Financial - January 2025")
- Keep titles concise but descriptive
- Use proper capitalization

#### URL Structure
- Use HTTPS URLs for security
- Ensure PDF files are accessible
- Test links after adding them

#### File Organization
- Group related documents together
- Maintain chronological order (newest first)
- Use consistent formatting across similar document types

### Advanced Customization

#### Adding Custom Styling
To add custom styles for new content types:

1. **Add CSS to the `<style>` section**:
   ```css
   /* Custom styling for new content type */
   .custom-content-link {
       /* Your custom styles here */
   }
   ```

2. **Apply the class to your HTML**:
   ```html
   <li><a href="..." class="list-item-link custom-content-link">
       <!-- content -->
   </a></li>
   ```

#### Modifying Transitions
To change the accordion animation speed or style:

```html
<!-- Faster transitions -->
x-transition:enter="transition ease-out duration-200"

<!-- Slower transitions -->
x-transition:enter="transition ease-out duration-500"

<!-- Different easing -->
x-transition:enter="transition ease-in-out duration-300"
```

#### Adding Icons
To add icons to document links:

```html
<li><a href="..." class="list-item-link">
    <div class="flex items-center">
        <svg class="w-4 h-4 mr-2" fill="currentColor" viewBox="0 0 20 20">
            <!-- SVG path data -->
        </svg>
        <strong>Document Title</strong>
    </div>
    <span class="text-blue-600 font-semibold">View PDF</span>
</a></li>
```

## Troubleshooting

### Common Issues

1. **Tab Not Showing**: Ensure the `activeTab` value matches between the button and content section
2. **Accordion Not Working**: Check that Alpine.js is loaded and `x-data="{ open: false }"` is present
3. **Styling Issues**: Verify Tailwind CSS is loading properly
4. **Links Not Working**: Test URLs in browser and ensure they're accessible

### Debugging Tips

- Use browser developer tools to check for JavaScript errors
- Verify that all Alpine.js attributes are properly formatted
- Test responsive behavior on different screen sizes
- Check that dark mode toggle works with new content

## Styling Modifications

### Dark Mode Customization
- Modify the `<style>` section in the HTML file
- Update Tailwind classes for layout changes
- Customize dark mode colors in the CSS variables

### Responsive Design
- Test on mobile, tablet, and desktop
- Use Tailwind's responsive prefixes (sm:, md:, lg:, xl:)
- Ensure content is readable on all screen sizes

## License

This project is maintained by the City of Miami. All rights reserved.

## Contributing

For questions or suggestions regarding the City of Miami's financial information, please contact the appropriate department through the official City of Miami website.

## Contact

- **Website**: [www.miamigov.com](http://www.miamigov.com)
- **Email**: webmaster@miamigov.com
- **ADA Support**: [ADA Public Notice](http://www.miamigov.com/ADA/Pages/PublicNotice/Policy.asp)

---

*Last updated: January 2025* 