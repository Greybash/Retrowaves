[phases.setup]
nixPkgs = [
  "python311",
  "gcc",
  "cmake",
  "libjpeg",
  "zlib",
  "lapack",
  "blas",
  "libx11",
  "boost",
  "openblas"
]

[phases.build]
cmds = [
  "pip install --upgrade pip",
  "pip install --no-cache-dir -r requirements.txt"
]

[start]
cmd = "gunicorn -b 0.0.0.0:8000 app:app"
