# H&M API Documentation

This API is listed on [Rapidapi](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/h-m-hennes-mauritz)
- https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/h-m-hennes-mauritz

## Table of Contents
1. [About H&M](#about-hm)
2. [API Overview](#api-overview)
3. [Technical Documentation](#technical-documentation)
4. [FAQs](#faqs)
5. [Best Practices](#best-practices)

## About H&M

### Company Overview
Hennes & Mauritz AB (H&M) is a multinational clothing retail company headquartered in Stockholm, Sweden. Founded in 1947 by Erling Persson, H&M has grown from a single women's clothing store called "Hennes" in Västerås, Sweden, to one of the world's largest fashion retailers. The company operates in over 75 markets worldwide with more than 4,000 stores and robust online presence.

### Business Model
H&M's business model is based on offering fashion-forward clothing at competitive prices through:
- Fast-fashion production and distribution
- In-house design team creating collections
- Sustainable fashion initiatives
- Multi-brand portfolio strategy
- Integrated digital and physical retail experience

### Brand Portfolio
- H&M: Main brand offering fashion for men, women, teenagers, and children
- COS: Higher-end minimalist fashion
- Weekday: Street fashion with a social awareness focus
- Monki: Colorful and creative youth-oriented fashion
- & Other Stories: Premium accessories and ready-to-wear collections
- ARKET: Modern-day market offering essential products
- H&M HOME: Interior design and decorations

### Sustainability Initiatives
H&M has committed to several sustainability goals:
- Circular fashion economy implementation
- Use of recycled materials
- Garment collecting program
- Conscious collection using sustainable materials
- Goal to use 100% recycled or sustainably sourced materials by 2030

## API Overview

### Purpose and Benefits
The H&M API provides developers with programmatic access to H&M's product catalog, enabling:
- Integration with e-commerce platforms
- Creation of fashion applications
- Product search and discovery tools
- Inventory management systems
- Price comparison services
- Fashion trend analysis applications

### API Features
1. Product Information
   - Detailed product descriptions
   - High-quality image access
   - Pricing information
   - Size availability
   - Material composition
   - Care instructions

2. Search Capabilities
   - Text-based search
   - Category browsing
   - New arrivals filtering
   - Similar product recommendations

3. Market Support
   - Multi-country support
   - Local pricing
   - Regional availability
   - Language localization

## Technical Documentation

# H&M API Documentation

## Overview
The H&M API provides access to product information, search functionality, and other features from the H&M retail platform. This documentation outlines the available endpoints, their parameters, and example responses.

## Base URL
The API is hosted on [RapidAPI](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/h-m-hennes-mauritz). 

https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/h-m-hennes-mauritz

Configure your client with the appropriate RapidAPI headers.

## Authentication
Required headers:
- `X-RapidAPI-Key`: Your RapidAPI key
- `X-RapidAPI-Host`: The H&M API host

## Common Parameters
- `countryCode`: Market/country code (default: 'en_us')
- Format: ISO country code (e.g., 'en_us', 'en_gb')

## Endpoints

### 1. Search Products
Get product search results based on a query.

```http
GET /search
```

#### Parameters
- `query` (required): Search term
- `page` (optional): Page number (default: '1')
- `perPage` (optional): Items per page (default: '36')
- `countryCode` (optional): Market code (default: 'en_us')

#### Response Format
```json
{
    "message": null,
    "data": [/* Product results */],
    "error": null
}
```

### 2. Search Suggestions
Get search suggestions based on a partial query.

```http
GET /search/suggestions
```

#### Parameters
- `query` (required): Search term (default: 'jack')
- `countryCode` (optional): Market code (default: 'en_us')

### 3. Product Description
Get detailed product information.

```http
GET /product/description
```

#### Parameters
- `productId` (required): Product ID (e.g., '1258254001')
- `countryCode` (optional): Market code (default: 'en_us')

### 4. Country Codes
Get available market codes.

```http
GET /country/codes
```

No parameters required.

### 5. Similar Products
Get products similar to a specified product.

```http
GET /product/similar
```

#### Parameters
- `productId` (required): Product ID (e.g., '1258254001')
- `countryCode` (optional): Market code (default: 'en_us')

### 6. Product Review Summary
Get review summary for a specific product SKU.

```http
GET /product/review/summary
```

#### Parameters
- `sku` (required): Product SKU (e.g., '1258254001002')

### 7. New Arrivals
Get new arrival products.

```http
GET /product/new-arrivals
```

#### Parameters
- `page` (optional): Page number (default: '1')
- `perPage` (optional): Items per page (default: '12')
- `countryCode` (optional): Market code (default: 'en_US')

### 8. Categories
Get product categories.

```http
GET /categories
```

#### Parameters
- `countryCode` (optional): Market code (default: 'en_us')

## Error Handling

The API returns standard HTTP status codes and error messages in the following format:

```json
{
    "message": "Error description",
    "data": null,
    "error": "ERROR_CODE"
}
```

Common error codes:
- `MISSING_PARAMETERS`: Required parameters are missing
- `BAD_REQUEST`: Invalid request parameters
- `INTERNAL_ERROR`: Server-side error

## Caching
The API implements caching for all endpoints. Cached responses will be returned when available to improve performance.

## Usage Example

Here's an example of how to search for products using cURL:

```bash
curl --request GET \
     --url 'https://apidojo-hm-hennes-mauritz-v1.p.rapidapi.com/search?query=dress&page=1&perPage=36&countryCode=en_us' \
     --header 'X-RapidAPI-Key: YOUR_API_KEY' \
     --header 'X-RapidAPI-Host: apidojo-hm-hennes-mauritz-v1.p.rapidapi.com'
```

## Rate Limiting
Please refer to your RapidAPI subscription plan for rate limiting details.

## FAQs

### General H&M Questions

**Q: What does H&M stand for?**
A: H&M stands for Hennes & Mauritz. "Hennes" means "hers" in Swedish, reflecting the company's origins as a women's clothing store. Mauritz was added after Erling Persson bought Mauritz Widforss, a hunting and fishing equipment store, in 1968.

**Q: How often does H&M release new collections?**
A: H&M typically releases new collections every season, with mini-collections and collaborations launched throughout the year. The API's new-arrivals endpoint is updated regularly to reflect these releases.

**Q: How does H&M handle sustainability in its product data?**
A: Sustainable products are marked with specific attributes in the API response, including materials used and conscious collection indicators. This information can be found in the product description endpoint.

**Q: What is H&M's market presence?**
A: H&M operates in over 75 markets with both physical stores and online presence. The API supports multiple country codes to provide market-specific data.

### API Technical FAQs

**Q: What is the rate limit for the API?**
A: Rate limits vary based on your RapidAPI subscription tier. Check your subscription details on RapidAPI for specific limits.

**Q: How often is the product data updated?**
A: Product data is updated multiple times daily to reflect inventory changes, new arrivals, and price updates. The API implements caching to optimize performance.

**Q: How should I handle product availability across different markets?**
A: Always include the countryCode parameter in your requests to ensure you receive market-specific availability and pricing. Product availability may vary by market.

**Q: What image sizes are available through the API?**
A: Product images are available in multiple resolutions. The product description endpoint returns all available image URLs and their corresponding dimensions.

**Q: How can I optimize API usage?**
A: Implement client-side caching, use appropriate page sizes, and cache responses according to your needs. The API already implements server-side caching to improve response times.

### Integration FAQs

**Q: Can I use the API for commercial purposes?**
A: Yes, the API can be used for commercial purposes subject to RapidAPI's terms of service and your subscription plan.

**Q: How should I handle currency conversion?**
A: The API returns prices in local currency based on the countryCode parameter. Currency conversion should be handled on the client side if needed.

**Q: What is the best way to handle product updates?**
A: Implement webhook listeners or regular polling of the product description endpoint for specific products you're tracking.

**Q: How can I test the API before going live?**
A: RapidAPI provides a testing console for all endpoints. Use this to familiarize yourself with the API responses before implementing.

## Best Practices

### API Usage

1. Optimization
- Implement client-side caching
- Use appropriate page sizes
- Batch requests when possible
- Monitor rate limits
- Handle errors gracefully

2. Data Handling
- Validate user inputs before making API calls
- Implement retry logic for failed requests
- Store frequently accessed data locally
- Keep track of API response times

3. Error Management
- Implement proper error handling
- Log API errors for debugging
- Provide user-friendly error messages
- Have fallback mechanisms

### Integration Tips

1. Getting Started
- Begin with basic endpoints
- Test thoroughly in development
- Implement gradual feature rollout
- Monitor API usage patterns

2. Performance Optimization
- Cache frequently accessed data
- Implement request queuing
- Use connection pooling
- Optimize payload size

3. Security Considerations
- Secure API keys
- Implement rate limiting
- Validate all user inputs
- Use HTTPS for all requests

### Common Use Cases

1. E-commerce Integration
```javascript
// Example of product search integration
async function searchProducts(query, page = 1) {
  try {
    const response = await fetch(`https://h-m-hennes-mauritz.p.rapidapi.com/search?query=${query}&page=${page}`, {
      headers: {
        'X-RapidAPI-Key': 'YOUR_API_KEY',
        'X-RapidAPI-Host': 'apidojo-hm-hennes-mauritz-v1.p.rapidapi.com'
      }
    });
    return await response.json();
  } catch (error) {
    console.error('Error searching products:', error);
    throw error;
  }
}
```

2. Product Recommendations
```javascript
// Example of similar products integration
async function getSimilarProducts(productId) {
  try {
    const response = await fetch(`https://h-m-hennes-mauritz.p.rapidapi.com/product/similar?productId=${productId}`, {
      headers: {
        'X-RapidAPI-Key': 'YOUR_API_KEY',
        'X-RapidAPI-Host': 'apidojo-hm-hennes-mauritz-v1.p.rapidapi.com'
      }
    });
    return await response.json();
  } catch (error) {
    console.error('Error fetching similar products:', error);
    throw error;
  }
}
```

### Market-Specific Considerations

1. Regional Pricing
- Handle multiple currencies
- Display appropriate tax information
- Consider market-specific discounts

2. Product Availability
- Check stock levels by market
- Handle regional restrictions
- Consider shipping limitations

3. Content Localization
- Use appropriate language codes
- Handle right-to-left languages
- Consider cultural preferences

### Future Considerations

1. API Evolution
- Stay updated with API changes
- Plan for version updates
- Monitor deprecation notices

2. Scalability
- Design for growth
- Implement caching strategies
- Consider load balancing

3. Monitoring
- Track API usage
- Monitor error rates
- Analyze performance metrics

This documentation provides a comprehensive overview of both H&M as a company and its API capabilities. Regular updates and improvements to this documentation will be made as new features and endpoints are added to the API.
