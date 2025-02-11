# Next.js 15 App Dir: Async Data Fetching Race Condition

This repository demonstrates a race condition that can occur in Next.js 15's `app` directory when using asynchronous data fetching with `getServerSideProps` alongside dynamic routes and server components.  The issue manifests as intermittent blank screens or incorrect UI rendering.

## Problem Description

The core problem lies in the timing of the client-side hydration process and the completion of server-side data fetching.  If the client attempts to hydrate the page before `getServerSideProps` has fully resolved the data, rendering inconsistencies will occur. This is exacerbated by the asynchronous nature of the data fetching and the dynamic nature of the route.

## Solution

The solution involves carefully managing the asynchronous operations and potentially adding safeguards to prevent early hydration.  This often requires a more robust loading state management system in your UI.