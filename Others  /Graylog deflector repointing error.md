## Graylog/Elasticsearch Deflector pointing error
![image](https://github.com/Miranda-Bai/ying-blog/assets/120993025/38d858c1-3c24-4b51-a1fc-bf1ac8ae2550)


![image](https://github.com/Miranda-Bai/ying-blog/assets/120993025/41a5b5a5-2fb8-4373-823e-915bbaf2ee83)

---

### Things to check

Check Elasticsearch is running on which port (default is 9200)

```
netstat -tuln
```

Check if the Elasticsearch index exists

```
curl "http://localhost:9200/gl-system-events_0/_settings"
```

Change read_only to false
```
curl -X PUT “localhost:9200/gl-system-events_0/_settings” -H ‘Content-Type: application/json’ -d ‘{ “index”: { “blocks”: { “read_only_allow_delete”: null } } }’
```

### Error remains
We created a new index and set the old index to "read_only". However, the deflector didn't repoint to the new index directly.
