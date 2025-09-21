# Intentional Prompting Documentation

This document demonstrates the intentional prompting techniques used during the development of the WeatherWise application, showcasing how strategic AI interactions led to improved code quality and functionality.

## Overview

Throughout the development process, I applied various intentional prompting strategies to guide AI assistance effectively. The following examples demonstrate key techniques that resulted in significant improvements to the codebase.

## Prompting Techniques Applied

### 1. Restate the Problem
**Technique**: Clearly restating the problem in my own words to ensure AI understanding.

**Example**:
- **Initial Prompt**: "Help me build a weather app"
- **Improved Prompt**: "I need to build a WeatherWise application for my Python course. The assignment requires me to create a weather advisor that combines weather data access with conversational AI capabilities. Can you help me understand the project requirements and suggest the best approach?"

**Result**: The AI provided a comprehensive breakdown of requirements and implementation options, leading to better project planning.

### 2. Identify Input/Output Requirements
**Technique**: Explicitly requesting clarification on function signatures and data structures.

**Example**:
- **Prompt**: "Can you help me implement the get_weather_data function first? I want to make sure I understand how to fetch and structure the weather data properly."
- **Follow-up**: "What should the function return? What error cases should I handle?"

**Result**: The AI provided detailed function specifications with proper error handling and data structure definitions.

### 3. Request Pseudocode
**Technique**: Asking for conceptual approaches before implementation.

**Example**:
- **Prompt**: "I need to implement the natural language parsing for weather questions. The function should extract location, time period, and weather attribute from user questions. Can you help me design a robust parsing system?"
- **Follow-up**: "What's the best approach for handling multi-word city names like 'New York City'?"

**Result**: The AI provided a multi-strategy approach using regex patterns and fallback mechanisms.

### 4. Challenge Edge Cases
**Technique**: Proactively identifying and requesting solutions for potential problems.

**Example**:
- **Initial Code**: Basic error handling in visualization functions
- **Challenge**: "How do we handle cases where the weather data might have missing fields or different structures? Should we add more robust error handling?"
- **Result**: Enhanced functions with multiple fallback strategies and comprehensive error handling

### 5. Request Modular Design
**Technique**: Asking for improvements to code organization and reusability.

**Example**:
- **Prompt**: "The current implementation has some basic error handling, but we can make it much more robust. Let me enhance the functions with better error handling and multiple fallback strategies."

**Result**: The AI provided enhanced versions with modular error handling and reusable components.

## Before/After Examples

### Example 1: Weather Data Retrieval Function

**Before (Initial AI Response)**:
```python
def get_weather_data(location, forecast_days=5):
    url = f"https://wttr.in/{location}?format=j1"
    resp = requests.get(url)
    return resp.json()
```

**Prompting Strategy**: "That looks good, but I'm concerned about making too many API calls during testing. Is there a way to add caching to avoid hitting the API repeatedly for the same location?"

**After (Improved Response)**:
```python
def get_weather_data(location: str, forecast_days: int = 5) -> Dict[str, Any]:
    # ... comprehensive implementation with:
    # - Input validation
    # - Caching mechanism
    # - Network error handling
    # - JSON parsing with error handling
    # - Data structure validation
    # - Clean, organized output format
```

**Why This Prompting Was Effective**: By identifying a specific concern (API call efficiency), I guided the AI to provide a more robust solution that included caching and comprehensive error handling.

### Example 2: Natural Language Parsing Function

**Before (Initial AI Response)**:
```python
def parse_weather_question(question):
    # Basic regex patterns for time and attributes
    # Simple location extraction
    return {"location": None, "time": "today", "attribute": None}
```

**Prompting Strategy**: "The time and attribute extraction looks comprehensive! But I'm concerned about location extraction. What if someone asks 'What's the weather like in New York City' or 'How's the temperature in San Francisco today?' - how will we handle multi-word city names?"

**After (Improved Response)**:
```python
def parse_weather_question(question: str) -> Dict[str, Optional[str]]:
    # ... enhanced implementation with:
    # - Multiple location extraction strategies
    # - Support for multi-word city names
    # - Fallback mechanisms
    # - Proper regex patterns for complex locations
    # - Normalization of common stopwords
```

**Why This Prompting Was Effective**: By challenging the edge case of multi-word locations, I prompted the AI to develop a more sophisticated parsing system that handles real-world scenarios.

### Example 3: Data Visualization Functions

**Before (Initial AI Response)**:
```python
def create_temperature_visualisation(weather_data, output_type='display'):
    # Basic matplotlib implementation
    # Minimal error handling
    plt.plot(days, temps)
    plt.show()
```

**Prompting Strategy**: "The visualizations look good! But I'm wondering about the data extraction. How do we handle cases where the weather data might have missing fields or different structures? Should we add more robust error handling?"

**After (Improved Response)**:
```python
def create_temperature_visualisation(weather_data: Dict[str, Any], output_type: str = 'display'):
    # ... enhanced implementation with:
    # - Multiple fallback strategies for temperature data
    # - Validation of temperature values before plotting
    # - Better error messages when data is missing
    # - Improved styling and formatting
    # - Label rotation for long date strings
    # - Location fallback handling
```

**Why This Prompting Was Effective**: By questioning the robustness of data handling, I prompted the AI to provide a production-ready solution with comprehensive error handling and multiple fallback strategies.

## Key Learning Outcomes

### 1. Strategic Questioning
By asking specific, targeted questions about edge cases and implementation details, I was able to guide the AI toward more robust solutions.

### 2. Iterative Improvement
Each conversation built upon previous work, with prompts designed to enhance existing functionality rather than starting from scratch.

### 3. Problem Decomposition
Breaking complex problems into smaller, manageable components allowed for more focused AI assistance and better solutions.

### 4. Real-World Considerations
Challenging the AI with practical concerns (API efficiency, multi-word locations, missing data) led to more production-ready code.

## Conclusion

The intentional prompting techniques applied throughout this project demonstrate how strategic AI interaction can lead to significantly improved code quality. By restating problems, identifying requirements, challenging edge cases, and requesting modular designs, I was able to guide the AI toward solutions that not only met the assignment requirements but also provided robust, production-ready functionality.

The before/after examples show that thoughtful prompting can transform basic implementations into comprehensive, error-resistant solutions that handle real-world scenarios effectively.
