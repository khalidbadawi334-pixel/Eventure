# TagLens: Cloud-Based Event Management System

## Overview
TagLens is a web application for planning and managing events such as conferences, weddings, and workshops. It provides organizers with tools to create event pages, sell tickets, and track RSVPs. The system leverages AWS serverless architecture for scalability and reliability.

## Features
- Organizers can create event pages, sell tickets, and track RSVPs
- S3 stores event images and brochures
- DynamoDB holds event details and user registrations
- CloudFront ensures fast content delivery globally
- Cognito authentication for organizers and attendees
- AWS Lambda processes payments and sends confirmations via SES
- SNS sends reminders to attendees before events

## AWS Architecture

TagLens is built on a modern, serverless AWS architecture designed to make event management seamless, secure, and scalable for everyone. Here’s how the pieces fit together:

**Amazon S3** is the digital gallery for your events. It safely stores all your event images, brochures, and even hosts the PHP frontend, making sure your content is always available and easy to update.

**Amazon CloudFront** acts as the global delivery service, ensuring that your event pages, images, and documents load quickly for users anywhere in the world. No matter where your attendees are, they get a fast, smooth experience.

**Amazon API Gateway** is the front door to TagLens’s backend. It exposes secure REST endpoints, allowing organizers and attendees to interact with the system—whether creating events, buying tickets, or checking RSVPs.

**AWS Lambda** is the brain behind the scenes. Whenever someone interacts with TagLens (like registering for an event or making a payment), Lambda functions spring into action to process requests, update records, and trigger notifications—all without the need for traditional servers.

**Amazon DynamoDB** is the memory of TagLens. It’s a fast, reliable NoSQL database that stores all your event details, user registrations, ticket sales, and RSVP data. DynamoDB scales automatically, so whether you’re hosting a small workshop or a massive conference, your data is safe and accessible.

**Amazon Cognito** keeps everyone’s accounts secure. Organizers and attendees can sign up, log in, and manage their profiles with confidence, knowing their information is protected by robust authentication.

**AWS IAM** (Identity and Access Management) is the security guard, making sure only the right people and services have access to sensitive data and operations. It enforces strict permissions and roles across the platform.

**Amazon SES** (Simple Email Service) is the messenger, sending out confirmations, receipts, and important updates to users after they register or purchase tickets.

**Amazon SNS** (Simple Notification Service) is the reminder system, sending timely notifications to attendees before events start, so nobody misses out.

**Amazon CloudWatch** is the eyes and ears of TagLens, monitoring activity, logging events, and helping troubleshoot any issues to keep everything running smoothly.

Together, these AWS services create a robust, flexible, and human-friendly platform that lets you focus on creating memorable events while the technology takes care of the rest.

## Getting Started
1. Clone the repository
2. Configure AWS credentials
3. Deploy infrastructure using AWS SAM or Serverless Framework
4. Update environment variables for AWS resources
5. Run the PHP frontend locally or deploy to S3

## Learning Outcomes
- Design scalable, event-driven serverless applications
- Implement API Gateway with Lambda for stateless execution
- Use DynamoDB as a managed NoSQL database
- Secure APIs with IAM roles and resource policies

## Project Structure
- `/backend` - Lambda functions (PHP via custom runtime or Node.js/Python wrappers)
- `/frontend` - PHP web app (can be hosted on S3)
- `/infrastructure` - CloudFormation/SAM templates
- `.github` - Copilot instructions and workflows

## Notes
- Replace placeholder AWS resource values with your own
- For Lambda, consider using Bref for PHP support
- Use environment variables for sensitive configuration

---
For architecture diagrams and deployment scripts, see `/infrastructure`.
