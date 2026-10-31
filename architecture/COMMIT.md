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
6. `0aad727 docs(agents): update macos platform guidance`
   - `AGENTS.md`
   - `TODO.md`
   - `architecture/COMMIT.md`
7. `09d28c1 feat(usage): support current agy token metadata`
   - `src/agyswap/cli.py`
   - `src/agyswap/usage.py`
8. `3675533 test(test): cover current agy token refresh`
   - `tests/test_swap.py`
9. `88aa18a docs(architecture): record agy 1.4.12 token shape`
   - `architecture/OBSERVE.md`
   - `architecture/SPEC.md`
10. Commit terakhir memperbarui rekaman commit ini:
   - `architecture/COMMIT.md`

## Alasan pengelompokan

Perubahan dipisah berdasarkan area: implementasi CLI, refresh token, test, metadata paket, dokumentasi user, dokumentasi arsitektur, lalu instruksi agent dan catatan commit. Commit kode tidak mencampur perubahan dokumentasi atau metadata.

## Validasi

- `uv run ruff format .`
- `uv run ruff check .`
- `uv run pytest -q` → 109 passed
- `uv build`
- Keychain macOS lokal terbaca tanpa mencetak token.
- `agyswap status --json` dari uv tool lokal mengenali login aktif tanpa mencetak email.

## Instalasi lokal

- `agyswap-cli` versi PyPI sebelumnya dihapus dengan `uv tool uninstall agyswap-cli`.
- Repository ini dipasang sebagai editable uv tool dengan `uv tool install --editable . --force`.
- Executable aktif: `/Users/alfan/.local/bin/agyswap`.

## Tidak di-commit

- `dist/` dan artefak build lain tetap di-ignore oleh repository.
- Verifikasi add/switch dengan dua akun Google nyata belum dilakukan karena akan mengubah Keychain dan login aktif user.
