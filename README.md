[Huggingface Scraper](https://apify.com/cloud9_ai/huggingface-scraper?fpr=data)

Search and extract ML models and datasets from Hugging Face Hub. Get model cards, download stats, tasks, and architectures.

## Features

- Extract data from [https://huggingface.co/api](https://huggingface.co/api)
- Multiple scraping modes: models, datasets
- Automatic rate limiting
- Proxy support via Apify Proxy

## Input Configuration

### Modes

1. **models**: /models?search={query}&limit={limit}&sort=downloads&direction=-1
2. **datasets**: /datasets?search={query}&limit={limit}&sort=downloads&direction=-1

### Example Input

```
{
  "mode": "models",
  "query": "example search",
  "maxResults": 20
}
```

## Output

The actor stores results in the Apify dataset. Each item contains:

- `id`
- `author`
- `sha`
- `lastModified`
- `private`
- `pipeline_tag`
- `tags`
- `downloads`
- `likes`
- `library_name`

## Usage Example

```
const input = {
  "mode": "models",
  "query": "example search",
  "maxResults": 20
};

const run = await ApifyClient.actor('huggingface-scraper').call(input);
const { items } = await ApifyClient.dataset(run.defaultDatasetId).listItems();

console.log(items);
```

## Limits

- Maximum results per run: 200
- Rate limiting: 1 request per second (default)

## Support

For issues or questions, contact the developer or open an issue on GitHub.

## License

Apache-2.0