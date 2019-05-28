# NodeJS + Minio

Provides Minio and NodeJS in a single image. Useful for CI.

Intended usage is Gitlab:

```|yml
.test_with_yarn:
  image: djflix/nodeminio:latest
  variables:
    MINIO_ACCESS_KEY: myaccesskey
    MINIO_SECRET_KEY: mysecretkey
  stage: test
  script:
    - "minio server /data &"
    - "yarn"
    - "yarn test"
```