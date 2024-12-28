# File Compression Web Application

This is a web application built using **Next.js** for the frontend and **Node.js** for the backend. The application allows users to upload files (PDF, JPEG, PNG, and MP4) and compress them using both lossless and lossy compression methods. The goal is to reduce the size of the files like how tools such as gzip or zip do, without significant loss of quality.

## Stack and Libraries Used

### Frontend:
- **Next.js**: React framework for building the frontend and backend API routes in the same project.
- **React**: For building the user interface (UI).
- **CSS/Styled Components**: For styling the application.

### Backend:
- **Node.js**: Server-side runtime environment.
- **Multer**: Middleware for handling file uploads.
- **Sharp**: Image processing library for compressing JPEG and PNG files.
- **Ghostscript**: Command-line tool for PDF compression (invoked via `child_process`).
- **ffmpeg**: For compressing MP4 video files (can be added to the backend if needed).
- **fs**: For file system operations such as reading, writing, and deleting files.

### Other Tools:
- **NPM**: Node.js package manager for managing dependencies.

## Approach

The approach is designed to allow seamless file compression for different file types (PDF, PNG, JPEG, MP4):

1. **Frontend (UI)**:
   - Users can upload a file via a file input form.
   - Users can choose between lossless or lossy compression options.
   - Once the file is uploaded and compressed, a download link is provided for the compressed file.

2. **Backend (API)**:
   - The backend is built using Next.js API routes.
   - Files are uploaded via **Multer** middleware to the server.
   - **Sharp** is used for image compression.
   - **Ghostscript** is used for compressing PDF files by invoking it via the `child_process` module.
   - **ffmpeg** (optional) can be used for compressing MP4 files.
   - After compression, the server sends the compressed file back to the user for download.

## Advantages
- **Multiple File Types Supported**: JPEG, PNG, PDF, and MP4 compression are supported.
- **Lossless and Lossy Compression**: Users can choose between lossless or lossy compression, providing flexibility based on their needs.
- **Fast Compression**: The application uses optimized libraries for fast compression, minimizing the wait time for users.
- **File Integrity**: The compression methods are chosen to minimize quality loss, ensuring the files remain usable.
- **Simple UI**: The frontend offers a simple and intuitive interface for uploading and downloading compressed files.
- **No Third-Party Tools for PDF**: By using **Ghostscript** directly via `child_process`, we avoid unsafe or deprecated npm packages.

## Achievements
- Users can upload PDF, PNG, JPEG, and MP4 files.
- Compression of PDF files using Ghostscript, JPEG/PNG files using **Sharp**, and MP4 files using **ffmpeg** (if configured).
- Lossless and lossy compression options for each file type.
- File download is automatically triggered after compression is complete.
- Temporary files are cleaned up after the download is completed to save server space.

## Enhancements that Can Be Made

### Frontend:
- **Progress Bar**: Implement a progress bar or spinner to show the user the compression progress.
- **File Preview**: Allow users to preview images (PNG/JPEG) and PDFs before and after compression.
- **Drag-and-Drop Upload**: Add drag-and-drop functionality for file uploads.
- **File Type Validation**: Add more robust file type validation on the frontend to ensure only supported formats are uploaded.

### Backend:
- **Support for More File Types**: Implement compression for additional file formats (e.g., DOCX, XLSX, etc.).
- **Batch Compression**: Allow users to upload multiple files at once and compress them in bulk.
- **Custom Compression Options**: Allow users to set custom compression parameters (e.g., quality, resolution, bitrate for videos).
- **API Rate Limiting**: Implement rate-limiting to prevent abuse or overuse of the compression service.
- **Error Handling and Logging**: Improve error handling and add logging for troubleshooting purposes.

### Other Enhancements:
- **Authentication**: Implement user authentication to track file compressions or limit the number of compressions per user.
- **File Size Estimation**: Show the estimated compressed file size before initiating the compression.
- **Docker Support**: Package the application in a Docker container for easy deployment.

## How to Run the Project

### Prerequisites
- Node.js and NPM installed on your system.
- Ghostscript and ffmpeg installed (for PDF and MP4 compression).

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/file-compressor.git
cd file-compressor
