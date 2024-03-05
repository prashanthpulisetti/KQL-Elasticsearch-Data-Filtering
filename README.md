# Kibana Query Language (KQL)

The Kibana Query Language (KQL) is a simple text-based query language designed for filtering Elasticsearch data. Unlike other query languages, KQL's primary role is data filtering; it does not handle aggregation, transformation, or sorting.

## Key Features:
- Filter data using free text search or field-based queries
- Suggests field names, values, and operators as you type
- Ideal for precise data retrieval

## Usage Examples:
- Filter documents where a value for a field exists: `http.request.method: *`
- Match specific values: `http.request.method: GET`
- Search within a range: `http.response.bytes < 10000`
- Combine multiple range queries: `http.response.bytes > 10000 and http.response.bytes <= 20000`

## Getting Started:
- Explore the KQL documentation for detailed syntax and examples
- Use KQL in Kibana's search bar for interactive queries

## Contributing:
- Contribute to KQL's development by submitting bug reports or enhancements
- Engage with the Kibana community on forums and discussions

## License:
Read More about [license here](https://github.com/prashanthpulisetti/KQL-Elasticsearch-Data-Filtering/blob/main/LICENSE)
