http://localhost:8000
    {
    "message": "PDF Processing API",
    "endpoints": {
        "POST /upload": "Upload and process a new PDF file",
        "POST /process-file": "Process an existing file from the input directory",
        "GET /list-files": "List all PDF files in the input directory",
        "GET /": "This information"
    }
    }


example:
curl -X POST "http://localhost:8000/upload/" \
     -H "accept: application/json" \
     -H "Content-Type: multipart/form-data" \
     -F "file=@./filein/aaa.pdf"

curl -X POST "http://localhost:8000/process-file/" \
     -H "accept: application/json" \
     -H "Content-Type: multipart/form-data" \
     -F "file=@./filein/TPW98705.pdf"

curl -X GET "http://localhost:8000/list-files/" \
     -H "accept: application/json" \
     -H "Content-Type: multipart/form-data" \

curl -X POST http://localhost:8000/process-all/

#get processing status
curl -X GET http://localhost:8000/processing-status/TPW98705.pdf

docker run -ti --rm --entrypoint sh -v ./filein:/filein_ocrmypdf sha256:9d0737314c6d414fd1226c769519a4afc14f28ebc09ed3991251ee20398344f2