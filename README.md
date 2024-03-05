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
**Kibana Query Language (KQL)** is a powerful tool for filtering and querying Elasticsearch data. Whether you’re investigating security incidents, analyzing logs, or monitoring performance, KQL simplifies the process. As an open-source project, we invite you to contribute by reporting bugs, enhancing features, and engaging with the Kibana community. Let’s collaborate to make KQL even better! 🚀👍

## License:
Read More about [license here](https://github.com/prashanthpulisetti/KQL-Elasticsearch-Data-Filtering/blob/main/LICENSE)
