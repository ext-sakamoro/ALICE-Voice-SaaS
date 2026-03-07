# ALICE-Voice SaaS

Voice-specialized procedural codec API

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-Voice |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/encode` | 音声データをパラメトリック圧縮 |
| `POST /api/v1/decode` | パラメータから音声復元 |
| `POST /api/v1/synthesize` | テキストから音声合成 |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
