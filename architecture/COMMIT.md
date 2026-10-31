# Commit

## Commit yang dibuat

1. `f6c1f17 feat(cli): add macos keychain backend`
   - `src/agyswap/cli.py`
2. `873460e test(test): add macos keychain coverage`
   - `tests/test_swap.py`
3. `e66d734 chore(package): add macos classifier`
   - `pyproject.toml`
4. `290a390 docs(project): document macos support`
   - `README.md`
   - `CONTRIBUTING.md`
5. `5a2ed8d docs(architecture): record macos keychain contract`
   - `architecture/OBSERVE.md`
   - `architecture/SPEC.md`
6. Commit terakhir mencatat aturan agent dan open work platform:
   - `AGENTS.md`
   - `TODO.md`
   - `architecture/COMMIT.md`

## Alasan pengelompokan

Perubahan dipisah berdasarkan area: implementasi CLI, test, metadata paket, dokumentasi user, dokumentasi arsitektur, lalu instruksi agent dan catatan open work. Commit kode tidak mencampur perubahan dokumentasi atau metadata.

## Validasi

- `uv run ruff format .`
- `uv run ruff check .`
- `uv run pytest -q` → 107 passed
- `uv build`
- Pembacaan Keychain macOS lokal berhasil tanpa mencetak token: prefix `go-keyring-base64`, panjang hasil terjaga.

## Tidak di-commit

- `dist/` dan artefak build lain tetap di-ignore oleh repository.
- Verifikasi add/switch dengan dua akun Google nyata belum dilakukan karena akan mengubah Keychain dan login aktif user.
